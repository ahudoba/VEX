AYTOMATING THE MANUFACTURING

1. Run 'Initialization_index_samples.m' to initialize the index for the number of samples

2. Run the 'number_of_samples.m' through which you declare the number of samples

3. Create the directories for the number of samples (number of Exhausts) through running 'make_exhaust_directories.m'

%%% AM*  3a. Run 'variables bounds'

4. Run 'transfer_stamping_files.m' to transer from the 'Nominal' Stamping directory ('Stamping') the files for the run of the permutation and the Stamping simulation 
to the 'Stampings' folder for each sample (each Exhaust)

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
(ns (please view 1.) with parts cotrained Executing 'templex_run.bat', running the 'read2_new_coords.parm' to copy the new coordinates encapturing the new Resonator(2122) or Stamping part(in case of Part16, Part17)
executing 'computation.bat' to run the Stamping simulation,Running 'reading_opt_part16.m', 'reading_opt_part17.m', 'reading_opt_part2122.m' enclosed in the 'RUN' directories as made in step 15c.

16a. Run the Stampings_run, which executes 'templex_run.bat', running the 'read2_new_coords.parm', 'computation.bat' in all the 'Exhaust_%d' directories
16b. Run the Thinning.m to get the Thinning(Response) out for each Exhaust.

Ensuring that ALL the Stamping simulations have run:
17. Create the directory 'Reliability_STAMPING' with the code 'make_Reliability_Stamping_Directory.m'
After entering ourselrves in the  'Reliability_STAMPING' directory
18. Run the Moonte_Carlo_Stamping.m within which the Monte_Carlo.m runs inside the Teliability_STAMPING, performing so the Monte Carlo Analysis in all 
Exhaust Stampings
19. Run the 'make_Surfaces_Stamping_Directory.m' to create the 'SURFACES' directory.
20. Run the 'Surface_Tradeoff_Stamping.m' to run within the 'Surface_Tradeoff.m' withing the folder 'SURFACES' used to create the relationship surfaces between 
the Design Variables and the Thinning for the Stampings. 

AUTOMATING THE BENDING SIMULATIONS
21. Run the 'Changing_Bending_tpl.m', prepared to run the permutations on the Bending pipes
22. Run the 'Copying_changed_beding_tpl.m' to copy 'read2_new_coords_key.m' in each Exhaust sample 'Exhaust_%d/Bendings'
23. Run the 'Bending_pipes_angles.m'
24. Run the 'Changing_Bending_key.m'
25. Rename the Bending directories through running the 'Renaming_Bending_Directories.m'
26. Run the Bend angle in the 'read2_new_coords_key.m' with running the 'Changing_Bend_Angle.m'

27. Running the 'Ascending_Thinning_Bending.m', as saved in 'Bending' directory.
28. Copy the 'Ascending_Thinning_Bending.m' to the 'Exhaust_%d/Bendings/Bending_1_i' with i=1,...,6, number of bends and after being modified to 
'Exhaust_%d/Bendings/Bending_2_j' with j=1,...,7.

29. Changing the MASTER Model with running 'Changing_MASTER_MODEL_tpl.m'






