# Raine's LBZ2 Death Egg Falling Cutscene
that scene where the death egg crashes into launch base but in Sonic 3 AIR (based on the Origins version, rather than the Sonic 3 Complete version)
y'know, like, some Origins Parity i guess! (but also not really.)

![mod in use](https://github.com/nabbup/LBZ2DeathEggFalling/blob/1f9978a866e6a1abca26452f66024694f2d676fb/mod%20in%20use.png)

## Side-notes
1. this isn't meant to replace the [Sonic 3 Complete LBZ Transition](https://gamebanana.com/wips/51834) mod that was released a long time ago.

it's moreso just my take on the idea, *based on* an official presentation of the cutscene in Sonic Origins, and in fact i'd be lying if i said the S3C-styled transition wasn't a reason behind making this.

2. Knuckles skips the cutscene when going through his own route of the level. the way it checks for that is the same as the base game, and it exclusively checks for that while the main character is Knuckles. mods can replace that check if they want to, mainly to skip over it for other characters. the function you use to do that is `function bool LBZ2.skipTransition()`

here's an example of what something using it would look like:
```
function bool LBZ2.skipTransition()
{
  if (global.characters == 4) // technically can be checking for anything as long as it exists in your mod already.
    return true // skip it
  return base.LBZ2.skipTransition() // calling this is VERY IMPORTANT. please do not leave it out of your mods :(
}
```
3. you can use `function string LBZ2.getBackgroundKey()`, `function string LBZ2.getMountainOverlayKey()`. and `function string LBZ2.getDeathEggSpriteKey()` to swap out the important graphics from the transition, namely the background, moutain overlay (the little bit that is in front of the Death Egg), and the Death Egg itself. this is mainly to provide a nice way for people to insert their own graphics, say for a specific character being in use or something.

you can find the functions near the top of the `main.lemon` script file if you want to do that.

4. i'm not trying to be 100% accurate to a given version of the LBZ transition, whether it's the Sonic 3 Complete version or the Sonic Origins version. it was just a goal of mine to make something that looked nice.
