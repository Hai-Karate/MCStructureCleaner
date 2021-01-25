# MCStructureCleaner

Modded structure cleaner for minecraft. Removes all references to non-existent structures to allow for clean error logs and chunk saving. The program goes through every chunk, in every region file of the world, removing the relevant `structure reference` and `structure start` tags.

Designed to fix worlds suffering from the [[MC-194811] Missing structures will destroy saved worlds](https://bugs.mojang.com/browse/MC-194811) bug, where uninstalling a mod which generated custom structures causes the world to become unstable.

Fixes errors such as `Unknown structure start: <missing structure>`, `Failed to save chunk`

# Usage

1. Install the requirements: [Python 3.x](https://www.python.org/) and [Matcool's Anvil Parser](https://github.com/matcool/anvil-parser).
2. Place main.py in the same directory as your world folder.
3. Run main.py, and instruct it as to which structure tag you wish to remove. I recommend using [NBTExplorer](https://github.com/jaquadro/NBTExplorer) to find the name.
   - -h For help on command line arguments.
   - -t For the tag you want removed, in quotes.
   - -j For the number of threads you want to run it on (default 4, recommended 2x the number of cores in your CPU).
   - Example: 
   ```
   python main.py -t "Better Mineshaft" -j 8
   ```
4. Let it run.
5. Replace the contents of your region folder with the contents of new_region.

# Todo:

- [x] More detailed output.
- [ ] Multiple tag input. (In progress)
- [x] Multithreading. (Thanks DemonInTheCloset!, now 2.8x faster)
- [x] Command line arguments. (Thanks DemonInTheCloset)
- [ ] Selection of world/dimensions.
- [ ] Allow for picking up progress where program left off.
- [ ] Checking disk space available.
- [ ] Auto-removal of all non vanilla structures mode.

# Notes:

- I have only tested this with 1.16 worlds.
- Feel free to message me on twitter if you need help using it.
- With large worlds, it may take a while to process, also depends on your hardware. 
