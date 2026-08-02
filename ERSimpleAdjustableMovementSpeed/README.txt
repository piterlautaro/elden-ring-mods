Practical c0000.hks edit from ividyon's HKS repository, originally made for personal use. I got off 200 hours of Nightreign and am now feeling that ER's movement is too slow for its scale. I looked around and most of the solutions were either larger mods or those that didn't work in my setup. Hopefully this could also help people scratch their Nightreign itch while playing through the whole of the Lands Between. It could probably be written more efficiently but I'm not a programmer.

What this does is it simply applies a movement speed multiplier to each of the player's movement stages (walking, running, and sprinting). By default, I've set it so that only sprinting is 50% faster, but it is very easy to change it anyway you want.

You don't have to download this if you already have a c0000.hks from another mod. You can just copy the edits. Also, Deflect Me Not has more thought-out movement changes built into the mod. I recommend checking that mod out if you want better implementation + highly configurable 'action RPG interactivity' to the game.

Standalone install (this is such a trivial edit I doubt anyone would bother):
1. Setup ME2 or ME3
2. Set the mod path to the folder where this README is located

Merging with other mods without c0000.hks:
1. Put the "action" folder into your current mod's folder

Merging with other c0000.hks:
1. Copy the following into the c0000.hks of your installed mod, JUST BEFORE the end of "function Move_onUpdate()"

-- MoveSpeedIndex 0 is for WALKING, 1 is RUN, 2 is SPRINT
-- CHANGE THE VALUE AFTER 2001, 1.5 means 150% faster
if GetVariable("MoveSpeedIndex") == 2 then
  act(2001, 1.5)
end
 
if GetVariable("MoveSpeedIndex") == 1 then
  act(2001, 1.0)
end
 
if GetVariable("MoveSpeedIndex") == 0 then
  act(2001, 1.0)
end
-- CHANGE THE VALUE AFTER 2001, 1.5 means 150% faster

2. Save

Keep in mind this does not affect the speed of the animations at all, only the distance travelled.

Massive thanks to ividyon and everyone else who made .hks editing accessible to the layperson. Huge thanks to ReiJr also, for making their work easy to understand and reference.