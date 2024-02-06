# test1_openlane
This is to present the demo on openlane tools.

openlane_new_tutorial
<br/>
<br/>To work with the openlane type in the terminal 
<br/>cd OpenLane
<br/>make mount
<br/>
<br/>To create the design type the following command in the terminal
<br/>./flow.tcl -design <design_name> -init_design_config -add_to_designs -config_file config.tcl
<br/>
<br/>To run openlane interactively
<br/>You may run the flow interactively by using the -interactive option:
<br/>./flow.tcl -interactive
<br/>
<br/>Then type the follwoing
<br/>
<br/>% package require openlane
<br/>
<br/>Then, you should be able to run the following main commands:
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
<br/>run_magic
<br/>The above commands can also be written in a file and passed to flow.tcl:
./flow.tcl -interactive -file <file>
<br/>
<br/>If the design is too small. you try appending these to your configuration file (config.tcl):
<br/>set ::env(FP_CORE_UTIL) 5
<br/>set ::env(PL_TARGET_DENSITY) 0.5
<br/>(low utilization)
<br/>Updating OpenLane
<br/>If you already have the repo locally, then there is no need to re-clone it. You can run the following:

<br/>cd OpenLane/
<br/>git checkout master
<br/>git pull
<br/>make
<br/>make test # This is to test that the flow and the pdk were properly updated

<br/>
[configuration variables](https://openlane.readthedocs.io/en/latest/reference/configuration.html)
