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
