# Final Fantasy VIII Playable Monsters & Devour Patcher

This table comes with a LUA trainer that makes playable monsters less glitchy, as well as assembly hacks that make the Devour skill always hit and work on any enemy. The table itself is filled with a lot of data and can be confusing, but it does have the addresses necessary to change out your party for a monster, redirect names, and customize battle encounters.

Currently, at least ``sixteen`` monsters are refined. Devour patching is 99% finished, unless I missed a spot.

This is set up for the US version and with a pointer for DuckStation 0.1-4918-g82965f74. You can swop the pointer out for any other emulator pointer that leads to the start of PSX RAM. Examples from older emulators are at the bottom of the table.

## Recommended GameShark Codes

### More Enemy Memory

Battles generally can only have up to two or three unique enemy models. If not using the battle memory code, you'll likely need to pause the emulator when the transition screen wipes and change "Enemies to Load" in the Cheat Table so your opponents have less variety. Even with the code on, you might get loud, glitchy monster sounds or even glitched textures if you're using expensive monsters like bosses.

If you use this code (Cheat Engine can't do it, needs frame perfection), you can make a fair bit of room for battle models. This assembly handles a pointer that constantly writes effect animation, it seems. It doesn't care at all if it's moved, so that frees up a lot of space that otherwise isn't used. However, this new location does use the third party member slot, so you may not be able to use this code and have a human party member in the third slot. Similarly, the enemy models might bleed into the first or even second party member's slot if you have too much going on.

```
More Enemy Memory {Kemui52}
C00BAE90 00008017
800B9194 00008019
800B919C 000054B0
800BAE90 00008019
800BAE94 000054B0
```

### Lock All Health

Several monsters have negative health, causing lag and autodeath. Use this combination of codes to brute force all health to maximum, as well as lock statuses.

```
Lock All Health
C005F146 00000003
900ED170 0000270F
900ED174 0000270F
900ED240 0000270F
900ED244 0000270F
900ED310 0000270F
900ED314 0000270F
00000000 0000FFFF
80078892 0000270F
80078894 0000270F
80078A62 0000270F
80078A64 0000270F
80078C32 0000270F
80078C34 0000270F
80077808 0000270F
3007789E 00000000
800778A0 0000270F
30077936 00000000
80077938 0000270F
300779CE 00000000
800779D0 0000270F
30077A66 00000000
80077A68 0000270F
30077AFE 00000000
80077B00 0000270F
30077B96 00000000
80077B98 0000270F
30077C2E 00000000
80077C30 0000270F
```

### Battle Camera Control

Some monsters are really big, so use this edited code to move the camera to a better view (I sped up the move speed and rearranged the buttons).

```
Battle Cam Control w/ Right Stick & L1/L2/R2 {LiquidManZero}
C005F146 00000003
C00ED14C 00000004
C20E3D80 0000000F
800E3D70 00000000
00000000 0000FFFF
C005F146 00000003
C00ED14C 00000004
D0082DEE 00000004
E2082DF0 00000040
100E3D80 00000020
D0082DEE 00000004
E3082DF0 000000C0
110E3D80 00000020
D0082DEE 00000004
E2082DF1 00000040
100E3D88 00000020
D0082DEE 00000004
E3082DF1 000000C0
110E3D88 00000020
D0082DEE 00000001
E2082DF0 00000040
100E3D82 00000020
D0082DEE 00000001
E3082DF0 000000C0
110E3D82 00000020
D0082DEE 00000001
E2082DF1 00000040
100E3D8A 00000020
D0082DEE 00000001
E3082DF1 000000C0
110E3D8A 00000020
D0082DEE 00000002
E2082DF0 00000040
110E3D84 00000020
D0082DEE 00000002
E3082DF0 000000C0
100E3D84 00000020
D0082DEE 00000002
E2082DF1 00000040
110E3D8C 00000020
D0082DEE 00000002
E3082DF1 000000C0
100E3D8C 00000020
```

## Known Quirks

todo: explain more of the quirks, like can't fight an enemy you're playing as or how weird the stats are or the unavoidable status menu lag or how summon can't be used at all if playing as a monster

## Credits

Most codes in the table were found by folks on GameHacking.org.

The data that I found are:
- Pointers for emulator RAM
- Size modifiers & in-game pointers
- Devour resistances and assembly
- Enemy AnimSet listings
- Command animations
- Battle name assembly

