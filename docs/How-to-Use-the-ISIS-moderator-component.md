[Mcstas mainpage](/mcstas/docs/index.md)


How to use the ISIS moderator component
=======================================

There have been many versions of the ISIS moderator component over the years and some of the 'early virtual moderator' components had various problems such as time offsets and difficulties dealing with super mirror guides. This page is not going to dwell on previous versions but just show the latest version which we believe to be correct. Importantly it will show you how to use this component correctly. 

If you don't have the latest version please download [commudus_1.comp](https://www.dropbox.com/s/7eucgnpbn8yf9o6/Commodus_I.comp?dl=0)

Correct example of its use;

COMPONENT Source =   Commodus_1(Face="msMerlin_160.mcstas", E0 = E_min, E1 = E_max, modXsize=0.12, modZsize = 0.12,  xw = 0.094, yh = 0.094, dist = 1.6)

This produces a neutron distribution at the ISIS TS1 or TS2 moderator face. The Face argument determines which TS1 or TS2 beamline is to be sampled by using corresponding Etable file. Neutrons are created having a range of energies determined by the E0 and E1 arguments. Trajectories are produced such that they pass through the moderator face (defined by modXsize and modZsize) and a focusing rectangle (defined by xw, yh and dist).

INPUT PARAMETERS:
 
 * Face:   (word)  filename of the moderator face you are using
 * E0:       (meV) Lower edge of energy distribution
 * E1:       (meV) Upper edge of energy distribution
 * modXsize: (m)   Moderator width
 * modZsize: (m)   Moderator height
 * xw:       (m)   Width of focusing rectangle
 * yh:       (m)   Height of focusing rectangle
 * dist:     (m)   Distance from source surface to the focusing rectangle

Note: By setting the E0, E1 and focusing window parameters correctly you will maximise the efficiency of your simulations. So if you have a high speed chopper which only lets through neutrons close to 5 mev then set E0=4.9 mev and E1=5.1 meV. Be careful that the energy width is wide enough so you are not under illuminating the chopper ! Similarly if you have a 1cm2 sample at 10m from the moderator and absorbing collimation down your beam line then set you focus window such that xw=0.01 yh=0.01 and dist=10. Its important to put the collimation in though in your simulations otherwise your 1cm2 sample will see the whole moderator face and the beam divergence will be wrong. 
