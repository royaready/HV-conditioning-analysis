Spinlab High voltage conditioning analysis code for the Ra EDM project
9/10/2020
Author: Roy Ready (roy.a.ready@gmail.com)

This analysis code calculates discharge rates and related quantities of electrodes being charged with a periodic bipolar power supply. 
It has been tested to process the high voltage conditioning data conducted at Spinlab (MSU, East Lansing) from 2017--2020.

MATLAB programs:
* batch_process_everything.m
* batch_process_hv_sim.m
* batch_process_hv_sim_nb23.m
* batch_process_hv_sim_nb56.m
* batch_process_hv_sim_nb78.m
* calc_discharge_rate.m
* calc_offset.m
* chunkify.m
* cumulative_discharge_rate_plotter.m
* find_charging_data.m
* find_discharges_final.m
* gaus_min_amp_avg_stdev.m
* hv_plot_xy_errors.m
* plot_discharge_hist.m
* RaEDM_leakage_analysis.m
* sort_state.m
* steady_state_plotter.m
* ti13_batch_process_hv_sim.m
* triplet_calculator.m
* wt_avg_stdev.m

To generate analysis files for one conditioning shift data file, run RaEDM_leakage_analysis.m.
batch_process_*.m will run a group of related conditioning shift files as a batch.
To generate a cumulative timeline plot:
1) collect the conditioning shift folders in a folder that you create in the same directory as cumulative_discharge_rate_plotter.m
2) Copy 2 data files from each analysis file and place them into the newly created folder. 
They are <timestamp>-discharge-rate-neg.txt and <timestamp>-discharge-rate-pos.txt
3) change the variable "analysis_folder_name_parent" in cumulative_discharge_rate_plotter.m to the name of the folder you created.
4) change the variable "electrodes" in cumulative_discharge_rate_plotter.m to the name of the electrodes you are analyzing.
5) run cumulative_dsicharge_rate_plotter.m

To generate a steady state leakage current vs. voltage plot:
6) copy <timestamp>-steady-state-v-voltage.txt from the new analysis folder created by cumulative_rate_discharge_plotter.m to a new folder. If you want to display multiple steady-state data series, run 1)->5) for each electrode pair and copy the steady state data files to the same directory.
7) in steady_state_plotter.m, change the name of variable "analysis_folder_name_parent" to the name of the folder you created for the steady-state data files.
8) manually change the call to hv_plot_xy_errors to the data series you would like to plot. 
9) run steady_state_plotter.m