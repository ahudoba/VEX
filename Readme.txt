AYTOMATING THE MANUFACTURING

1. Run 'Initialization_index_samples.m' to initialize the index for the number of samples

2. Run the 'number_of_samples.m' through which you declare the number of samples

3. Create the directories for the number of samples (number of Exhausts) through running 'make_exhaust_directories.m'

4. Run 'transfer_samping_files.m' to transer from the 'Nominal' Stamping directory ('Stamping') the files for the run of the permutation and the Stamping simulation 
to the 'Stampings' folder for each sample(each Exhaust)

5. Run 'transfer_bending_files.m' to transer from the 'Nominal' Bending directory ('Bendings') the files for the run of the permutation  
to the 'Bendings' folder for each sample(each Exhaust)
but also 
files from the 'MASTER' model (whole Exhaust) to the 'Nominal' MASTER directory ('MASTER') for each Exhaust
 It is noteworthy to mention at this point that we presume tht the thickness where consdered a new variable for a component of the Exhaust is sampled by a sequence of Gaussian Distributions at 5 different levels (0.5, 0.8, 1.0, 1.2, 1.5).
Solutions (thickness values) which lie in the intersection regeion among two consecutive gaussian distributions are coded to be substitued but an obtain value picked from a random permutation of values
lie among the distributions. (Note X)

6a.Sampling the Thickness for the Stampings (Resonator Shells Thickness) while running 'Sampling_thickness_stamping.m'.
6b. Running the 'Thickness_Stamping_Reject_Gaussian_random.m' to check if there are rejected values for the Stamping Thickness but also work out their replacements
(please view (Note X))

7. In this occasion only for this recent stage we considered Thickness for the Frog pipes as tested to Bending 5 different values 0.5, 0.8, 1.0, 1.2, 1.5. 
(*Bending simulations need to run for extra thicknesses in scale (0,0.1,0.2,0.3,0.4,0.5,0.6,....1.5) and that's why only 5 of them are considered here.
However, for the existing situation the sampling is coded with the 'Sampling_Thickness_Bending_pipe.m'
8. Considering the (Note X) we sample the thickness for each other component while running the:
a, 'Gaussian_random.m' and subsequently b, 'Reject_Gaussian_random.m'
a, 'ThX_Gaussian_random.m' and subsequently b, 'ThX_Reject_Gaussian_random.m'
.....................................................
a, 'Th7_Gaussian_random.m' and subsequently b, 'Th7_Reject_Gaussian_random.m',
where X=1,..,7

9.Sample the Stampings, the Resonators variables(features of their design) while running 'Sampling_stamping.m'
10. Sample the Bendings, Bending pipes and their accompanying Radius of tool while running 'Sampling_Diameter_Radius_Thickness_Bending.m'
11. Sample the lines of Holes while running 'Sampling_lines_holes.m'
12.a. Enclose all the samples in the Permutations Matrix while running 'Permutation_Matrix.m'
b. Please run also ' Permutation_Matrix_in_mat_file.m'

13a. Assign the samples to the *.tpl file for the Stamping Part 16 with running 'Changing_Part16_tpl.m'
13b. Assign the samples to the *.tpl file for the Stamping Part 17 with running 'Changing_Part17_tpl.m'
13b. Assign the samples to the *.tpl file for the Stamping Parts 21,22 (one of the two resonators) with running 'Changing_Part2122_tpl.m'

14. Changing the thickness to the thickness samples for the Stampings in the *.parm files while running 
'Changing_Part16_parm.m', 'Changing_Part17_parm.m', 'Changing_Parts2122_parm.m'
15. Copying 'reading_opt_part16.m', 'reading_opt_part17.m', 'reading_opt_part2122.m'
with running 'make_exhaust_stamping_RUN_directories.m while opening the 'RUN' directories in each Exhaust

16. Performing permutations in 'Exhaust_%d/Stampings/Part16', 'Exhaust_%d/Stampings/Part17', 'Exhaust_%d/Stampings/Part21,22' where '%d' is the typed number of the sample
(ns (please view 1.) 

17a. Executing 'templex_run.bat'
17b.Running the 'read2_new_coords.parm' to copy the new coordinates encapturing the new Resonator(2122) or Stamping part(in case of Part16, Part17)
17c. Executing 'computation.bat' to run the Stamping simulation
17d. Running 'reading_opt_part16.m', 'reading_opt_part17.m', 'reading_opt_part2122.m' enclosed in the 'RUN' directories as made in step 15c.

Ensuring that ALL the Stamping simulations have run:
18. Create the directory 'Reliability_STAMPING' with the code 'make_Reliability_Stamping_Directory.m'
After entering ourselrves in the  'Reliability_STAMPING' directory

19. Run the 'Monte_Carlo_0.m' to assign our response for the Stampings, their Thinning also to vectors
20. Run the 'Monte_Carlo_Correlation_coefficients.m' with aim to obtain the Correlation Matrix with enclosed information for the relatioship of 
Variables to the Response
21. Run the 'Monte_Carlo_Histogram.m' to extract the Thinning spectrum in Histogram
22. Run the 'Monte_Carlo_Feasibility.m'  to work out the Feasible solutions
23. Run the 'Surface_Tradeoff.m' to get the 3D surface of the Thinning with the (Design) Variables such to indicate likely the pairs for the solutions which drive Thinning
such that this satisfies the manufacturing Thinning constraint

AUTOMATING THE BENDING SIMULATIONS
24. Run the 'Changing_Bending_tpl.m', prepared to run the permutations on the Bending pipes
25. Run the 'Copying_changed_beding_tpl.m' to copy 'read2_new_coords_key.m' in each Exhaust sample 'Exhaust_%d/Bendings'
26. Run the 'Bending_pipes_angles.m'
27. Run the 'Changing_Bending_key.m'
28. Rename the Bending directories through running the 'Renaming_Bending_Directories.m'
29. Run the Bend angle in the 'read2_new_coords_key.m' with running the 'Changing_Bend_Angle.m'

31. Running the 'Ascending_Thinning_Bending.m', as saved in 'Bending' directory.
32. Copy the 'Ascending_Thinning_Bending.m' to the 'Exhaust_%d/Bendings/Bending_1_i' with i=1,...,6, number of bends and after being modified to 
'Exhaust_%d/Bendings/Bending_2_j' with j=1,...,7.

33. Changing the MASTER Model with running 'Changing_MASTER_MODEL_tpl.m'






