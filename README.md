SC2_lang
========

Localization for Steve's Carts 2. Interested in translating the mod into your language, then follow the basic instruction below.


How to translate the mod

1. Pull the en_Us.lang file

2) Rename it to match your language. If you're not sure what the name should be, take a look at the lang files of minecraft and use the same name.

3) Translate all the entries to your language

4) Put your lang file in the lang folder of Steve's Carts

5) Run minecraft, swap yo your language and see if it look good.

6) Make a pull request to this repository (github.com/Vswe/SC2_lang/) to submit your changes.



Notes about syntax
------------------

When you edit the lang files you might encounter some special syntax in it. See the line below for instance

info.SC2:complexityOverloadError=[%1] is too complex for this hull.

The tag [%1] means that something will be put their by the code. It could be anything but usually it's quite easy to get it from the context.
In the above example the tag will be replaced by the name of the module which is too complex for the hull. This allows you to move this name around.
If it would make more sense to say something like "The hull can't handle the complexity of Coal Engine" in your language then you would simply add
"The hull can't handle the complexity of [%1]". In some cases the tag will be in the middle of a sentence, this allows you to make the word/nuumber 
appear where it should. Sometimes there might be multiple tags, these are then replaced with different content. Like in the following example where
2 module names are involved.

info.SC2:missingParentError=[%1] requires [%2] to work!


Furtheremore, there might be some bigger type of tags. Take a look at the example below.

info.SC2:occupiedSides=Will occupy the [%1] [%2:side|sides]

In the example we first have a normal tag with index 1, but then the second tag looks weird. The first tag will simply be replaced by the sides of the cart
the module will occupy. This might be one side or multiple sides. If it's just one side we want it to say "side" but if there are multiple sides we want it
to say "sides". This is exactly what the second tag does, if we have one side it will use the first part ("side") of the tag, otherwise it will use the second part ("sides").


No matter if we have one side or multiple sides we will use the sequence "Will occupy the" in the beginning. In some languages a world like "the" will be
different depending on if we have plural or singular. This can be handle by adding more tags with the very same index. Take a look at the forged example below.

info.SC2:occupiedSides=Will occupy [%2:the|THE] [%1] [%2:side|sides]

In the example, there are now two tags with index 2. Let's say a specific module will occupy the Top side, then the sentence will be "Will occupy the Top side". 
However, let's imagine the module also occupied the Front side. That would give use the message "Will occupy THE Top and Front sides". Another example where
this is used can be seen in the real example below. This entry could however be done with just one longer tag instead.

info.SC2:moduleGroupToolShooter=[%1:Tool|Tools] or [%1:Shooter|Shooters]

There's also a third version of the tag which is quite similar to the second. take a look at the example below.

modules.attachments.SC2:cageAutoPickUp=[%1->Activate|Deactivate] auto pick up

Instead of the colon in the plural/singular tag there is now an arrow. This means that the option is not picked depending on if we have multiple items or not. The option
is picked depending on something else. In this case whether the auto pick up for the cage module is active or not. The good thing with this type of tag is that it allows
multiple options (of course you need to use the same number of options as you find in the english file). An example of multiple options can be seen below.

modules.tanks.SC2:creativeTankMode=Current creative mode: [%1][%2->Normal|Always full|Always empty|Always half]

Note that all different types of tags can only be used if they are in the original entry. You can't add it whereever you please since then it won't be replaced by anything.
If you find the tags in the english entry, then you can move them around or add multiple ones of the longer versions if you so like. Just keep the indices.


