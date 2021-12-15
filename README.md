# Cubic-Local-Binary-Pattern
Cubic-LBP source code (MATLAB).

This function is to compute the Cubic-LBP features for a video sequence.

If you use this MATLAB code, please cite the following publication:
V. Esmaeili and S.O. Shahdi, “Automatic micro-expression apex spotting using Cubic-LBP,” Multimedia Tools and Applications, pp. 1-9, 2020.

Reference: 

(The original paper):

V. Esmaeili and S.O. Shahdi, “Automatic micro-expression apex spotting using Cubic-LBP,” Multimedia Tools and Applications, pp. 1-9, 2020.

Copyright 2020 by Vida Esmaeili & Seyed Omid Shahdi.
Matlab version was Created by Vida Esmaeili.
If you have any problem, please feel free to contact Vida Esmaeili or Seyed Omid Shahdi.
Seyed Omid Shahdi:
shahdi@qiau.ac.ir

Vida Esmaeili:
V.Esmaeili@qiau.ac.ir

%% %%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%

Function: Running this funciton each time to compute the Cubic-LBP distribution of one video sequence.

Inputs:

"VolData" keeps the grey level of all the pixels in sequences with [height][width][Length];
please note, all the images in one sequnces should have same size (height and weight).
But they don't have to be same for different sequences.

"FxRadius", "FyRadius" and "TInterval" are the radii parameter along X, Y and T axis; They can be 1, 2, 3 and 4. "1" and "3" are recommended.
Pay attention to "TInterval". "TInterval * 2 + 1" should be smaller than the length of the input sequence "Length".


"NeighborPoints" is the number of the neighboring points in plane1, plane2, plane3, plane4, plane5, plane6, plane7, plane8, plane9, plane10, plane11, plane12, plane13, plane14 and plane15; They can be 4, 8, 16 and 24. "8" is a good option. For example, NeighborPoints = [8 8 8 8 8 8 8 8 8 8 8 8 8 8 8];

"TimeLength" and "BoderLength" are the parameters for bodering parts in time and space which would not be computed for features. Usually they are same to TInterval and the bigger one of "FxRadius" and "FyRadius";

"bBilinearInterpolation": if use bilinear interpolation for computing a neighboring point in a circle: 1 (yes), 0 (no).

"Bincount": For example, if XYNeighborPoints = XTNeighborPoints = YTNeighborPoints =...NeighborPoints= 8, you can set "Bincount" as "0" if you want to use basic LBP, or set "Bincount" as 59 if using uniform pattern of LBP, If the number of Neighboring points is different than 8, you need to change it accordingly as well as change the above "Code".
"Code": only when Bincount is 59, uniform code is used.
Output:

"Histogram": keeps Cubic-LBP distribution of all the pixels in the current frame with [15][dim];
here, "15" deote the fifteen planes of Cubic-LBP, i.e., plane1, plane2, ..., plane15.
Each value of Histogram[i][j] is between [0,1] (it is normallised in this way)



