# Wire-wrapped-fuel-pin-CFD-DMD
The code and data of 'Modal analysis of lead-bismuth eutectic flow  in a single wire-wrap rod channel'

Our code have files as follow:

1.CFD result demo

  1.1.main rod
  
     cen2-30000 .plt contains the variable data(velocities and static pressure) and the information of mesh units at T=3.0s. 
     cen11-cen12,cen2,cen3,cen4,cen5,cen6 are one-sixth surface of main rod.
     
  1.2.plane at Z=0.131
  
     planemid-30000 .plt contains the variable data(velocities and static pressure) and the information of mesh units at T=3.0s. 
     planemid represent the midle plane in axial direction.
     
  1.1.wire
  
     wire2-30000 .plt contains the variable data(velocities and static pressure) and the information of mesh units at T=3.0s. 
     wire11-wire12,wire2,wire3,wire4,wire5,wire6 are one-sixth surface of the middle wire.
     
2.data_manage_code

   transform the data in .plt files to Matlab.
   
3.DMD_code

   compute_DMD_velocity.m
   Use DMD Method to cauculate the velocity of middle section.

   compute_DMD_wire.m
   Use DMD Method to cauculate the pressure of wire.

   compute_DMD_wirewrap.m
   Use DMD Method to cauculate the pressure of the wirewrap fuel pin.

   lambda.m
   Cauclate the DMD mode.

   time_ave.m
   Cauculat the time averaged velocity of middle section by DMD data.
   
4.postprocess

   save_data.m
   transform the DMD data from Matlab to .dat (which Tecplot could read)

   wire_tecplot
   contains the .dat file about the postprocess of wire pressure and cross section velocity.
   
5.postprocess_picutre

   fuel pin
   Comparison of pressure counter on fuel pin surface between CFD and DMD at t=3s.

   velocity
   Comparison of three direction velocity on cross section between CFD and DMD at t=3s.

   wire
   Comparison of pressure counter on wire surface between CFD and DMD at t=3s.
   
6.actual service condition

6.1.This file include the snapshot matrix of U+, V+, W+ and P in the middle cross section.
  
  The snapshot matrix of U+, V+, W+, P are Data_u, Data_v, Data_w, Data_p, respectively.
  
6.2.compute_DMD_wirewrap.m is the main function of DMD method, and it contains the way to output variable information as .txt.
  and it contains the mehtod to cauculate the confficient of determination(R^2).

6.3.The midplane.dat contain the xyz position of each point and the grid information in cross section (The format of Tecplot).

6.4.If you want to post process in Tecplot, you have to paste the variable information in txt file to midplane.dat.(For example midplane_DMD.dat and midplane_real.dat)
  midplane_real.dat is CFD result, midplane_DMD.dat is DMD prediction.
