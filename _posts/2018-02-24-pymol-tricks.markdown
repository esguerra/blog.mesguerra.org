---
title: pymol tricks
date: 2018-02-24 21:25:00 +01:00
tags:
- pymol
- pymol tricks
- pymol python
- molecular visualization
---

I am a bit embarrassed to confess how long I have been using **pymol** for. It's certainly been quite a long time, somewhere around ten years. In those years I've compiled my own cheat-sheet, which I have abandoned somewhat. Now I'm giving a go to markdown and translating my old cheat sheet into a new one but with the same old tricks.




### General 

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


### Labels  

```python
label (n;C1'), "%s" % (name)
set label_color, black
set label_font_id, 4	
set label_size, 3
set label_position, [2,0,0]
show labels
```


### Spheres  

```python
set sphere_scale, 0.25
```


### Sticks  

```python
show sticks, selectionname
set stick_radius, 0.1
set stick_ball, on #Makes the stick command show ball and stick
set stick_ball_ratio, 1.5
```


### Ribbons  

```python
set ribbon_color, marine
set ribbon_width, 2
set ribbon_sampling, 1
set ribbon_smooth, 1
```


### Cartoon  

```python
cartoon putty
set cartoon_ladder_mode, 0
set cartoon_transparency, 0.5
set cartoon_ring_finder, 0
cartoon dumbbell
set cartoon_dumbbell_width, 0.2
set cartoon_dumbbell_radius, 0.4
set cartoon_color, marine, resi 34-67
set cartoon_color, blue, resi 68,78
show cartoon
```


### Ray tracing  

```python
set ray_trace_mode, 3
set ray_trace_fog,0
set ray_shadows,0
set depth_cue, 0              #This one with care or it might look funky.
set antialias,1
set ray_trace_gain, 0.005
png img1.png, width=1600, height=1200, dpi=600, ray=1
```


### Rotating ("turn" to rotate all loaded objects, "rotate" for individual objects)   

```python
turn x, 10
```


### Surfaces  

```python
set transparency, 0.65, i. 1-100
set cgo_transparency, 0.4
```


### Aligning Structures (They must have the same number of atoms and be the same molecule)  

```python
pair_fit rna2////C5, rna1////C5, rna2////C4, rna1////C4
pair_fit (rna2 and id 12+56), (rna1 and id 12+56)
```


### Displaying all states in a multi-state pdb, say, an NMR file and coloring by B-factor.  

```python
set all_states, on
spectrum b, yellow_white_red, minimum=48, maximum=100
spectrum b, rainbow2_rev
```

### Loading multiple pdb files into a multistate object (allfiles) using the python glob module  

```python
import glob
for x in glob.glob("Folder/*.pdb"): cmd.load(x, "allfiles")
```


### Draw a trace cartoon (or ribbon) based on atoms different than P or Calpha.  

```python
set cartoon_trace_atoms      #Note that ribbon_trace_atoms also works
cartoon tube
show cartoon, selection and name C1'
```


### Count atoms  

```python
select catoms, name c*
print cmd.count_atoms("catoms")
```


### Showing a slider after loading a trajectory  

```python
set movie_panel=1
#movie.add_state_sweep(1,0,start=1)
movie.add_state_loop(1,0,start=1)
set movie_panel_row_height, 20
```

### Show values of a setting   

```python
print setting.get_setting_text("gamma")
```

