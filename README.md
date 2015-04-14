# QGIS Command Bar

[![Join the chat at https://gitter.im/g-sherman/qgiscommand](https://badges.gitter.im/Join%20Chat.svg)](https://gitter.im/g-sherman/qgiscommand?utm_source=badge&utm_medium=badge&utm_campaign=pr-badge&utm_content=badge)

Adds a simple interactive command bar to QGIS.  Commands are defined as Python code and may take arguments.

All functions are interactive and if not all arguments are given will prompt for each one as required.

When defining a interactive functions questions can be added using the `command.command` decorator

```
@command.command("Question 1", "Question 2")
def my_function(arg1, arg2):
    pass
```

The new function can be called in the command bar like so:

`my-function Hello World`

The command bar will split based on space and the first argument is always the function name, the rest are arguments passed to the function.

The command bar also has auto complete for defined functions, and tooltips once I get that to work correctly

You can use `CTRL + ;` to open and close the command bar.

## TIPS

You can also alias a function by calling the `alias` function in the command bar.

`alias mypoint point-at 100`
 
 `point-at` is a built in function that creates a point at `x y` however we can alias it so that it will be pre-called with the x argument set. Now when we call `mypoint` we only have to pass the `y` each time.

```
-> mypoint
(point-at) What is the Y?: 200
```

Pro Tip:

You can even alias the alias command

```
-> alias & alias
& mypoint 100
```

`&` is now the shortcut hand for `alias`

## User functions

In a future version I will load user functions from a `.qgis2/python/qgiscommand` folder. Open to pull requests for that feature.

## NOTE

This is a work in progress and mainly a quick brain dump to play around with the idea.  

# TODO

- Save alias comamnds to disk
- User function location
- Tests
- More tests
- Docs
- More functions

Open to pull requests
