# Cellular Vehicle-to-Everything Traffic Generator

An SDR-based C-V2X Traffic Generator based on [srsLTE](https://github.com/srsLTE/srsLTE).

![TU Dortmund University](img/tu-dortmund_small.png "TU Dortmund University")
![Communication Networks Institute](img/CNI_small.png "Communication Networks Institute")
![SFB 876](img/SFB876_small.png "Collaborative Research Center SFB 876")
![DFG](img/DFG_small.png "DFG")


The work on this paper has been partially funded by Deutsche Forschungsgemeinschaft (DFG) within the Collaborative Research Center SFB 876 project B4.

# Installation

The build dependencies are the same as for srsLTE and can be found [here](https://github.com/srsLTE/srsLTE#build-instructions).

### Download and build:
```
git clone https://github.com/FabianEckermann/cv2x-traffic-generator.git
cd cv2x-traffic-generator
mkdir build
cd build
cmake ../
make
```

### Install:
```
sudo make install
```

### Update Libraries
You may need to update the libraries that your system can access. This is accomplished simply using:
```
sudo ldconfig
```


# Usage

The traffic generator can be used with static settings
```
   cv2x_traffic_generator -a clock=gpsdo -s 0 -l 5
```
or with a configuration file (an example config file is included in this repository)
```
   cv2x_traffic_generator -a clock=gpsdo -i sf_config.csv -o logfile.csv
```

## Help
The help menu is as follows:
```
Usage: cv2x_traffic_generator [acdgilmnoprs] -f tx_frequency_hz -v verbose
	-a RF args [Default ]
	-c N_sl_id [Default 19]
	-d RF devicename [Default ]
	-g RF Gain [Default 80.00 dB]
	-i input_file_name for csv file containing sub_channel_start_idx and l_sub_channel.
	-l l_sub_channel [Default 2]. If input_file_name is specified this will be ignored.
	-m mcs_idx [Default 20]
	-n num_sub_channel [Default for 50 prbs 10]
	-o log_file_name.
	-p nof_prb [Default 50]
	-r use_standard_lte_rates [Default 0]
	-s sub_channel_start_idx [Default 0]. If input_file_name is specified this will be ignored.
```

# Cite as

If you use this traffic generator in your research, please cite the following paper:

<!-- F. Eckermann, C. Wietfeld, ["SDR-based open-source C-V2X traffic generator for stress testing vehicular communication"](https://www.kn.e-technik.tu-dortmund.de/.cni-bibliography/publications/cni-publications/Eckermann2021sdr-based.pdf), In 2021 IEEE 93rd Vehicular Technology Conference (VTC-Spring), Helsinki, Finland, April 2021. -->

F. Eckermann, C. Wietfeld, "SDR-based open-source C-V2X traffic generator for stress testing vehicular communication", In 2021 IEEE 93rd Vehicular Technology Conference (VTC-Spring), Helsinki, Finland, April 2021.

### Bibtex:

	@InProceedings{Eckermann2021sdr,
		Author = {Fabian Eckermann and Christian Wietfeld},
		Title = {{SDR}-based open-source {C-V2X} traffic generator for stress testing vehicular communication},
		Booktitle = {2021 IEEE 93rd Vehicular Technology Conference (VTC-Spring)},
		Year = {2021},
		Address = {Helsinki, Finland},
		Month = {April}
	}
