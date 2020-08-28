# Python Q&A

## What's \_\_name\_\_ and \_\_main\_\_ ?
When a Python interpreter reads a Python file, it first sets a few special variables. Then it executes the code from the file.  

Python files are called modules and they are identified by the .py file extension. A module can define functions, classes, and variables.  

So when the interpreter runs a module, the ```__name__``` variable will be set as  ```__main__``` if the module that is being run is the main program.  

But if the code is importing the module from another module, then the ```__name__```  variable will be set to that module’s name.  

```python
# Python file one module

print("File one __name__ is set to: {}" .format(__name__))
```
<p align="center">
  file_one.py
</p>

By running this file you will see exactly what we were talking about. The variable ```__name__``` for this module is set to ```__main__```:

```python
File one __name__ is set to: __main__
```

Now add another file named file_two.py and paste this code inside

```python
# Python module to import

print("File two __name__ is set to: {}" .format(__name__))
```
<p align="center">
  file_two.py
</p>

Also, modify the code in file_one.py like this so we import the file_two module:

```python
# Python module to execute
import file_two

print("File one __name__ is set to: {}" .format(__name__))
```

<p align="center">
  file_one.py
</p>

The result should look like this:

```python
File two __name__ is set to: file_two
File one __name__ is set to: __main__
```

But run file_two directly and you will see that its name is set to ```__main__```:

```python
File two __name__ is set to: __main__
```

The variable ```__name__``` for the file/module that is run will be always ```__main__```. But the ```__name__``` variable for all other modules that are being imported will be set to their module's name.
