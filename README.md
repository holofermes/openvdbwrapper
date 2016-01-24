## OpenVDBWrapper
A collection of extensions that provide a higher level wrapping for `OpenVDB`.
There are three extensions: `OpenVDBGeometry`, `OpenVDBInlineDrawing`, and `OpenVDBWrapper`.

##### Requires: 
 - OpenVDB (https://bitbucket.org/holofermes/kl-externals).

## OpenVDBGeometry
 - defines a new `Geometry` type `VDBVolumes`
 - extends [`BaseAttribute`](http://docs.fabric-engine.com/FabricEngine/2.0.1/HTML/KLExtensionsGuide/Geometry/BaseAttribute.html) with FloatGridAttribute
 - `SpatialQueryable` implementations in VDBVolumesLocation.kl are a fluff, and VDBVolumesMarching.kl, which is kind of made from [RenderModules](https://github.com/dreamworksanimation/openvdb/blob/master/openvdb/viewer/RenderModules.cc) is, at least conceptually, to be considered the closest thing to `SpatialQueryable`.

## OpenVDBInlineDrawing
 - basic integration with [`InlineDrawing`](http://docs.fabric-engine.com/FabricEngine/2.0.1/HTML/KLExtensionsGuide/InlineDrawing/intro.html#inlinedrawing-extension-intro).
 - extends [`InlineShapeBase`](http://docs.fabric-engine.com/FabricEngine/2.0.1/HTML/KLExtensionsGuide/InlineDrawing/InlineShapeBase.html) with `InlineVDBVolumesShape`
 - extends [`InlineShapeAdaptor`](http://docs.fabric-engine.com/FabricEngine/2.0.1/HTML/KLExtensionsGuide/InlineDrawing/InlineShapeAdaptor.html) with `InlineVDBVolumesShape`

## OpenVDBWrapper
 A collection of structs and functions that implement the OpenVDB extension directly.


## dfg

To regenerate the dfg extensions run
```bash
extsringlength=5
for fold in $( ls Exts/*/ -d)
do
    ext=${fold:$extsringlength}
    ext=${ext%%/}

    rm -rf dfg/$ext
    mkdir -p dfg/$ext
    kl2dfg -polymorphism Exts/$ext/$ext.fpm.json dfg/$ext
done
```



Copyright
---------
This software is released under the MIT licence

Copyright (c) 2016 Fabio Piparo

Permission is hereby granted, free of charge, to any person obtaining a copy of 
this software and associated documentation files (the "Software"), to deal in 
the Software without restriction, including without limitation the rights to 
use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of 
the Software, and to permit persons to whom the Software is furnished to do so, 
subject to the following conditions:

The above copyright notice and this permission notice shall be included in all 
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR 
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS 
FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR 
COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER 
IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN 
CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.