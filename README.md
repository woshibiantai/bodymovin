# bodymovin
Experimenting with the interactivity of [bodymovin](https://github.com/bodymovin/bodymovin).

The test can be seen [here](https://woshibiantai.github.io/bodymovin/).

## Getting element
By including a hex at the front of the name (e.g. `#thisElement`), we can access this layer
in Javascript by calling `document.getElementById('thisElement')`. With that, we can interact
with that specific layer created in after Effects. The dragging example of the [experiment](https://github.com/bodymovin/bodymovin) shows how this works.

## Using animationData
`animationData` is a property of the animation object created when using bodymovin.
This property contains information of the layers created in After Effects,
hence allowing us to manipulate certain properties of the layer (e.g. position).


Note: In order for you to manipulate the animationData, the object has to have keyframes at the very start and the very end.
The keyframes can have a position difference of just 0.1, but there has to be a change for it to work.

#### More about the data
Here are some properties of the object you get from `animationData`:

Name | Type | Description
--- | :---: | ---
assets | Array | Contains objects with information of each asset used in After Effects
layers | Array | Contains objects with information of each layer created in After Effects
nm | String | Name of the After Effects composition


Here are some properties of the object you get from `animationData.layers[i]`:


Name | Type | Description
--- | :---: | ---
ks | Object | Contains keyframe information defined in After Effects (e.g. position, opacity, rotation, etc.)
nm | String | The name of the layer defined in After Effects


Note: The keyframe properties in ks are represented by a single letter (i.e. p for position and so on),
and the coordinates may or may not be found directly, depending on how the After Effects object was made


#### After Effects rigging
Rigging up a character or object is a method for animators to simply the animation process.
A [quick tutorial can be seen here](https://youtu.be/IJgAUkjsomA). These rigs allow us to interact with the
bodymovin object in a more interesting manner. For example, by using the [Joysticks 'n Sliders](http://aescripts.com/joystick-n-sliders/) plugin, we can map the controllers to the cursor or the
scroll, allowing users to animate the bodymovin object interactively.
Kittons on Codepen is a great example of [this](https://codepen.io/airnan/pen/EmdXGo).


Another plugin that would be awesome is [DUIK by Rainbox](https://rainboxprod.coop/en/tools/duik/).
Kittons also has an example for [this](https://codepen.io/airnan/pen/pyMgzN).
