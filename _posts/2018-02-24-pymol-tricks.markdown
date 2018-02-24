---
title: pymol tricks
date: 2018-02-24 21:25:00 +01:00
---

## General 

```python
bg white                       # Turn background color to white
save rna6.pse                  # Save your working session to pse file
set valence, 1                 # Show double bonds.
h_add                          # Show hydrogens.  
pymol -qc bla.pml >& bla.log & # To invoke without X11 display
pymol -M                       # Invoke mono mode instead of stereo. Avoid flicker.
unbond (id 8), (id 2)          # To remove a bond between atoms
bond (id 8), (id 2)            # To create a bond between atoms
select carbons, symbol c       # Select all carbon atoms and call them carbons.
color black, carbons           # Color the carbons selection black.
disable selectionname          # Hides/disables a loaded structure(selection).
enable selectionname           # Shows/enables a loaded structure(selection).
set internal_gui, 0            # Hide object control panel
```