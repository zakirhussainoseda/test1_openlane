# test1_openlane
This is to present the demo on openlane tools.

openlane_new_tutorial
<br/>
<br/>To lauch the openlane command prompt type in the terminal where the OpenLane folder is
cd OpenLane
make mount
<br/>
<br/>To create the design type the following command in the terminal
<br/>./flow.tcl -design <design_name> -init_design_config -add_to_designs -config_file config.tcl
<br/>
<br/>To run openlane interactively
<br/>You may run the flow interactively by using the -interactive option:
<br/>./flow.tcl -interactive
<br/>
<br/>A tcl shell will be opened where the openlane package is automatically sourced:
<br/>
<br/>Then type the follwoing
<br/>
<br/>% package require openlane
<br/>
<br/>Then, you should be able to run the following main commands:
<br/>
<br/>Any tcl command.
<br/>
<br/>prep -design <design> -tag <tag> -config <config> -init_design_config -overwrite
<br/>
<br/>similar to the command line arguments, design is required and the rest is optional
<br/>
<br/>run_synthesis
<br/>run_floorplan
<br/>run_placement
<br/>run_cts
<br/>run_routing
<br/>write_powered_verilog  " followed by "  set_netlist $::env(routing_logs)/$::env(DESIGN_NAME).powered.v 
<br/>
<br/>write_powered_verilog -output_def -output_nl -output_pnl
<br/>
<br/>run_magic
<br/>run_magic_spice_export
<br/>run_magic_drc
<br/>run_lvs
<br/>run_antenna_check
<br/>
<br/>The above commands can also be written in a file and passed to flow.tcl:
./flow.tcl -interactive -file <file>
<br/>
<br/>If the design is too small. you try appending these to your configuration file (config.tcl):
<br/>set ::env(FP_CORE_UTIL) 5
<br/>set ::env(PL_TARGET_DENSITY) 0.5
<br/>(low utilization)
<br/>
If these don't work, you may want to take a look at:
https://github.com/efabless/openlane/blob/master/regression_results/README.md
and explore different utilizations and densities.
<br/>
To launch kalyout
XDG_SESSION_TYPE=x11 klayout
<br/>
Updating OpenLane
If you already have the repo locally, then there is no need to re-clone it. You can run the following:

cd OpenLane/
git checkout master
git pull
make
make test # This is to test that the flow and the pdk were properly updated
