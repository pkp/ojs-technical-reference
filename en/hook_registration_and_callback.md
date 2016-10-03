# Hook Registration and Callback

The above example serves as a clear illustration of hook registration and callback; along with the list of hooks below, this should provide all the required information for extending OJS using hooks. However, there are a few important details that need further examination.

The process by which a plugin registers against a hook is as follows:

**Example 5.3. Hook Registration Process**

````
HookRegistry::register(
    'Templates::Manager::Index::ManagementPages',
    array(&$this, 'callback')
);
````

In the example above, the parameters to ``HookRegistry::register`` are:

1. The name of the hook. See the complete list of hooks below.
2. The callback function to which control should be passed when the hook is encountered. This is the same callback format used by PHP's ``call_user_func`` function; see the documentation at http://php.net for more information. It is important that ``$this`` be included in the array by reference, or you may encounter problems with multiple instances of the plugin object.

The definition of the callback function (named and located in the above registration call) is: