	Dandy Fighter -- TSB (The Strongest Battlegrounds) moveset. Just execute it (re-executing replaces the previous run).

	M1 ..... your TSB M1 animations are swapped for the Dandy attacks: hit 1 -> Attack1, hit 2 -> Attack2, hit 3 -> Attack3,
	         hit 4 -> Attack3 again (PLACEHOLDER, see M1_MAP). The damage is still TSB's own M1; only the animation changes,
	         and it is timed to the length of the TSB animation it replaces, so the combo keeps its normal speed.
	Block ... TSB's own block animation (10470389827) drives Dandy's block: while it plays Dandy blocks, when it stops Dandy stops.
	Walk .... Dandy's idle, walk and stop-walk replace the game's while you are on the ground. Emotes (and, by default, any other
	         action animation such as dashes or hit reactions) pause every custom animation until they are done.
	Moves ... your hotbar is replaced (like your template does) by 3 Dandy moves, made with the Custom Weapon library:
	         1 Dash   2 Charge   3 Leap
	         They are movement + animation only: TSB deals damage on the server, so these moves do not hurt anyone.

	The Dandy MODEL is embedded too (as a standard LZ4 .rbxm, decoded at run time and loaded with writefile + getcustomasset +
	GetObjects). It follows your character and does what your character does: every joint of your real body is mirrored onto
	Dandy, so he performs the Dandy M1s and moves AND the game's own animations, and his corrupt arm uses the baked Dandy
	animations. Your real avatar is hidden on YOUR screen only (other players still see your avatar doing the animations).
	Without writefile / getcustomasset the moveset still works, you just do not get the model.

	How the animations work: the Dandy animations are baked into this script (nothing is loaded from private asset ids) and
	are applied straight to your own character's joints right after the game's Animator writes them each frame, so they
	override it. Your parts replicate from you, so other players see it too.
	They only touch the six standard R6 joints (TSB characters are R6); the corrupt arm / flower head are not part of a TSB
	avatar, so they are left out.
