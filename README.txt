Impact Melt Degassing & O₂ Consumption — Quick Run Guide

Authors:
William Jo¹²³, Chenguang Sun¹³, Timothy Goudge¹³

Date: 2025-08-15

Affiliations:
¹ Department of Planetary and Geological Sciences, UT Austin
² Department of Aerospace Engineering and Engineering Mechanics, UT Austin 
³ Center for Planetary Systems Habitability, UT Austin


Overview:
This project simulates the effects of impact melt degassing on planetary oxygen consumption in the Archean and provides post-processing scripts for analysis and visualization of the results.

The workflow consists of:
Simulation Code – Runs Monte Carlo impact scenarios, calculates oxygen consumption from impact melt degassing, and stores results.
Post-Processing Code – Aggregates and analyzes simulation output, generates summary statistics, and produces publication-quality figures.

Sections:
1. Impact Fluxes — build per-Myr flux arrays.
2. Simulating Impacts — Monte Carlo impacts, save per-seed.
3. Impact Melt Generation — compute melt from impacts, save per-seed.
4. O₂ Consumption — calculate degassing O₂, save per-seed & averages.
5. Impact Properties — per-impact tables (type, size, melt, O₂).
6. Cooling Curves — convolve O₂ loss with half-Gaussian cooling.
7. Size/O₂ by Class — aggregate counts/melt/O₂ by size bin & type.

Tips:
- Recommended to run the workflow section-by-section (Total of 7 Sections)
- Use mod_seed_input_section_X and mod_seed_init_section_X to override seed and seed counts.
- Re-run any section if its inputs exist in sim_output/.

Outputs in sim_output/ include:
- seed_impact_<seed>.mat — per-seed impacts
- melt_gen_<seed>.mat — melt per Myr
- O2_consumed_melt_option_<opt>_<seed>.mat — per-Myr O₂
- impact_summary_seed_<seed>.mat — impactor details

Outputs in post_proc_output/ include:
- impact_O2_loss_response_<N>_sims.mat — cooling curves
- impact_count_1_10_25_<N>_sims.mat — size bin stats

File Structure:
impact_melt_degassing_O2_project/
├── impact_melt_degassing_O2_consumption_simulation_20250815_v1.mlx			# Main simulation script
├── impact_melt_degassing_O2_consumption_postprocess_20250815_v1.mlx         		# Post-processing and plotting scripts
├── sim_output/           								# Raw simulation results (.mat files)
├── post_proc_output/     								# Processed data & intermediate results
├── datasets/             								# Input datasets (e.g., Excel, CSV)
├── plots/                								# Figures generated during post-processing
└── README.md      

Revision History - List and Describe Revisions (by Date):

