# Python–GTK+3 中的微调器

> 原文:[https://www.geeksforgeeks.org/python-spinner-in-gtk-3/](https://www.geeksforgeeks.org/python-spinner-in-gtk-3/)

Gtk。微调器显示图标大小的旋转动画。它经常被用作 GtkProgressBar 的替代，用于显示不确定的活动。我们可以使用 **Gtk。Spinner.start()** 启动， **Gtk。Spinner.stop()** 停止动画。

**示例:**

## 蟒蛇 3

```py
import gi

gi.require_version("Gtk", "3.0")
from gi.repository import Gtk

class SpinnerAnimation(Gtk.Window):
    def __init__(self):

        Gtk.Window.__init__(self, title="GFG")
        self.set_border_width(3)
        self.connect("destroy", Gtk.main_quit)

        self.button = Gtk.ToggleButton(label="Start Spinning")
        self.button.connect("toggled", self.on_button_toggled)
        self.button.set_active(False)

        self.spinner = Gtk.Spinner()

        self.grid = Gtk.Grid()
        self.grid.add(self.button)
        self.grid.attach_next_to(
            self.spinner, self.button, Gtk.PositionType.BOTTOM, 1, 2
        )
        self.grid.set_row_homogeneous(True)

        self.add(self.grid)
        self.show_all()

    def on_button_toggled(self, button):

        if button.get_active():
            self.spinner.start()
            self.button.set_label("Stop Spinning")

        else:
            self.spinner.stop()
            self.button.set_label("Start Spinning")

myspinner = SpinnerAnimation()

Gtk.main()
```

**输出:**

<video class="wp-video-shortcode" id="video-465581-1" width="665" height="374" preload="metadata" controls=""><source type="video/webm" src="https://media.geeksforgeeks.org/wp-content/cdn-uploads/20200806214057/python-gtk-spinner.webm?_=1">[https://media.geeksforgeeks.org/wp-content/cdn-uploads/20200806214057/python-gtk-spinner.webm](https://media.geeksforgeeks.org/wp-content/cdn-uploads/20200806214057/python-gtk-spinner.webm)</video>