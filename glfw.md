# glfw

## Integrate with Vulkan

- dub.sdl:

```sdl
(...)
dependency "bindbc-glfw" version="~>0.9.0"
dependency "erupted" version="~>2.0.54"
versions "BindGLFW_Static" "GLFW_32"
libs "glfw3"
```

- Source:

```
import erupted;
public import bindbc.glfw;
mixin(bindGLFW_Vulkan);
```
