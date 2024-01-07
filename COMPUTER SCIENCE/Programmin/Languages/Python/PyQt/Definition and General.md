PyQt is a python for [Qt](https://wiki.qt.io/About_QtQt) which is a set of C++ libraries and development tools providing platform-independent abstractions for graphical user interfaces (GUIs).

```shell
$ python -m venv venv
$ venv\Scripts\activate
$ python -m pip install pyqt6
```

PS> python -m venv venv
PS> venv\Scripts\activate
(venv) PS> python -m pip install 

## Application[](https://realpython.com/python-pyqt-gui-calculator/#creating-your-first-pyqt-application "Permanent link")

Now that you have a working PyQt installation, you’re ready to create your first GUI app. You’ll create a `Hello, World!` application with Python and PyQt. Here are the steps that you’ll follow:

1. Import [`QApplication`](https://www.riverbankcomputing.com/static/Docs/PyQt6/api/qtwidgets/qapplication.html) and all the required widgets from [`PyQt6.QtWidgets`](https://www.riverbankcomputing.com/static/Docs/PyQt6/api/qtwidgets/qtwidgets-module.html).
2. Create an instance of `QApplication`.
3. Create your application’s GUI.
4. Show your application’s GUI.
5. Run your application’s [event loop](https://www.riverbankcomputing.com/static/Docs/PyQt6/api/qtcore/qcoreapplication.html?highlight=main%20loop#the-event-loop-and-event-handling), or main loop.

# Widgets

PyQt has a large collection of widgets. At the time of this writing, there are over [forty](https://www.riverbankcomputing.com/static/Docs/PyQt6/api/qtwidgets/qwidget.html) available for you to use to create your application’s GUI. Here, you’ve studied only a small sample. However, that’s enough to show you the power and flexibility of PyQt. In the next section, you’ll learn how to lay out different widgets to build modern and fully functional GUIs for your applications.

# Layout Managers

Now that you know about widgets and how they’re used to build GUIs, you need to know how to arrange a set of widgets so that your GUI is both coherent and functional. In PyQt, you’ll find a few techniques for laying out the widgets on a form or window. For instance, you can use the `.resize()` and `.move()` methods to give widgets absolute sizes and positions.

However, this technique can have some drawbacks. You’ll have to:

- Do many manual calculations to determine the correct size and position of every widget
- Do extra calculations to respond to window resize events
- Redo most of your calculations when the window’s layout changes in any way

Another technique involves using `.resizeEvent()` to calculate the widget’s size and position dynamically. In this case, you’ll have similar headaches as with the previous technique.

The most effective and recommended technique is to use PyQt’s [layout managers](https://realpython.com/python-pyqt-layout/). They’ll increase your productivity, mitigate the risk of errors, and improve your code’s maintainability.

**Layout managers** are classes that allow you to size and position your widgets on the application’s window or form. They automatically adapt to resize events and GUI changes, controlling the size and position of all their child widgets.

PyQt provides four basic layout manager classes:

1. [`QHBoxLayout`](https://www.riverbankcomputing.com/static/Docs/PyQt6/api/qtwidgets/qhboxlayout.html)
2. [`QVBoxLayout`](https://www.riverbankcomputing.com/static/Docs/PyQt6/api/qtwidgets/qvboxlayout.html)
3. [`QGridLayout`](https://www.riverbankcomputing.com/static/Docs/PyQt6/api/qtwidgets/qgridlayout.html)
4. [`QFormLayout`](https://www.riverbankcomputing.com/static/Docs/PyQt6/api/qtwidgets/qformlayout.html)
