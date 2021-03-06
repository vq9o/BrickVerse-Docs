# ModuleScript

A ModuleScript is a type of Lua source container that runs once and must return exactly one value. This value is then returned by a call to `require` given the ModuleScript as the only argument. ModuleScripts run once and only once per Lua environment and return the exact same value for subsequent calls to `require`.

ModuleScripts are essential objects for adhering to the don’t-repeat-yourself (DRY) principle. When you write a function, write it only once and use it everywhere. Having multiple copies of a function is disastrous when you need to change that behavior. So, you should define functions or groups of functions in ModuleScripts and have your Scripts and LocalScripts call `require` on your ModuleScripts. Keep your code organized!

It’s important to know that return values from ModuleScripts are independent with regards to LocalScripts and Scripts, and other environments like the Command Bar. Using `require` on a ModuleScript in a LocalScript will run the code on the client, even if a Script did so already on the server. Similarly, in BrickVerse Studio, using `require` on a ModuleScript in the hierarchy with the Command Bar will give a similar behavior. So, be careful if you are using a ModuleScript on the client and server at the same time, or debugging it within Studio.

Note that the first call to `require` on a ModuleScript will not yield (halt) unless the ModuleScript yields (e.g. calls `wait`). The current thread that called `require` will yield until a ModuleScript returns a value. A run time error is generated if this doesn’t happen. If a ModuleScript is attempting to `require` another ModuleScript that in turn tries to `require`s it, the **thread will hang and never halt (cyclic `require` calls do not generate errors).** Be mindful of your module dependencies in large projects!

If a ModuleScript object is has its Name property set to ‘MainModule’ and is uploaded to BrickVerse as a model to your account, Scripts can use `require` with the uploaded model’s AssetId instead. This allows you to create private modules on your BrickVerse account!

## Properties

Inherited from [Dynamic ](https://docs.brickverse.co/bricklua-lua-references-manual/dymanic)Set

Inherited from [Script Dynamics ](script-dynamics.md)Set
