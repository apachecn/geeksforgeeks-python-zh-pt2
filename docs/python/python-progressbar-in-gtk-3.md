# Python–GTK+3 中的 progress bar

> 原文:[https://www.geeksforgeeks.org/python-progressbar-in-gtk-3/](https://www.geeksforgeeks.org/python-progressbar-in-gtk-3/)

ProgressBar 用于显示长时间运行操作的进度。Gtk。ProgressBar 可以在两种不同的模式下使用–

*   **百分比模式**
*   **活动模式。**

当一个应用程序可以确定还剩多少工作时，我们可以使用 Gtk。百分比模式下的进度栏。在这种模式下，应用程序需要调用 **Gtk。ProgressBar.set_fraction()** 定期更新进度条，传递一个介于 0 和 1 之间的浮点数来提供新的百分比值。

当应用程序无法确定要做的工作量时，它可以使用活动模式，该模式通过在进度区域内来回移动的块来显示活动。在这种模式下，应用程序需要调用 **Gtk。ProgressBar.pulse()** 定期更新进度条。我们可以选择步长，用 **Gtk。progress bar . set _ pulse _ step()**方法。默认情况下，Gtk。进度条是水平的，从左到右，但是你可以用 **Gtk 把它变成垂直的进度条。progress bar . set _ orientation()**方法。使用 **Gtk 可以改变进度条的增长方向。ProgressBar.set_inverted()。** Gtk。ProgressBar 也可以包含文本，可以通过调用 **Gtk 进行设置。ProgressBar.set_text()** 和 **Gtk。progress bar . set _ show _ text()**。

**示例:**

## 蟒蛇 3

```py
from gi.repository import Gtk, GLib
import gi

# Since a system can have multiple versions
# of GTK + installed, we want to make
# sure that we are importing GTK + 3.
gi.require_version("Gtk", "3.0")

class ProgressBarWindow(Gtk.Window):
    def __init__(self):
        Gtk.Window.__init__(self, title="ProgressBar Demo")
        self.set_border_width(10)

        vbox = Gtk.Box(orientation=Gtk.Orientation.HORIZONTAL, spacing=6)
        self.add(vbox)

        # Create a ProgressBar
        self.progressbar = Gtk.ProgressBar()
        vbox.pack_start(self.progressbar, True, True, 0)

        # Create CheckButton with labels "Show text",
        # "Activity mode", "Right to Left" respectively
        button = Gtk.CheckButton(label="Show text")
        button.connect("toggled", self.on_show_text_toggled)
        vbox.pack_start(button, True, True, 0)

        button = Gtk.CheckButton(label="Activity mode")
        button.connect("toggled", self.on_activity_mode_toggled)
        vbox.pack_start(button, True, True, 0)

        button = Gtk.CheckButton(label="Right to Left")
        button.connect("toggled", self.on_right_to_left_toggled)
        vbox.pack_start(button, True, True, 0)

        self.timeout_id = GLib.timeout_add(50, self.on_timeout, None)
        self.activity_mode = False

    def on_show_text_toggled(self, button):
        show_text = button.get_active()
        if show_text:
            text = "Geek For Geeks"
        else:
            text = None
        self.progressbar.set_text(text)
        self.progressbar.set_show_text(show_text)

    def on_activity_mode_toggled(self, button):
        self.activity_mode = button.get_active()
        if self.activity_mode:
            self.progressbar.pulse()
        else:
            self.progressbar.set_fraction(0.0)

    def on_right_to_left_toggled(self, button):
        value = button.get_active()
        self.progressbar.set_inverted(value)

    def on_timeout(self, user_data):
        """
        Update value on the progress bar
        """
        if self.activity_mode:
            self.progressbar.pulse()
        else:
            new_value = self.progressbar.get_fraction() + 0.01

            if new_value > 1:
                new_value = 0

            self.progressbar.set_fraction(new_value)
        return True

win = ProgressBarWindow()
win.connect("destroy", Gtk.main_quit)
win.show_all()
Gtk.main()
```

**输出:**

<video class="wp-video-shortcode" id="video-465532-1" width="665" height="374" preload="metadata" controls=""><source type="video/webm" src="https://media.geeksforgeeks.org/wp-content/cdn-uploads/20200806195922/python-progess-bar-gtk.webm?_=1">[https://media.geeksforgeeks.org/wp-content/cdn-uploads/20200806195922/python-progess-bar-gtk.webm](https://media.geeksforgeeks.org/wp-content/cdn-uploads/20200806195922/python-progess-bar-gtk.webm)</video>