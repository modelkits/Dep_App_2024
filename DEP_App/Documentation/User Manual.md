# User Manual
![Control Panel](https://raw.githubusercontent.com/modelkits/Dep_App_2024/main/DEP_App/Documentation/Pics/Control%20Panel.png "Control Panel")

*Control Panel*

The control panel of PC_Main.vi from the PC Core folder of LabVIEW project allows you to configure the parameters of signals, system operating modes, parameters for saving data streams and the activity log, as well as visually monitor all parameters of the system and signals. It consists of the following blocks:

1. [Device Settings](#device-settings)
2. [Device Control](#device-control)
3. [Experiment's Info and recording settings](#experiments-info-and-recording-settings)
4. [Signal Generator Settings](#signal-generator-settings)
	* [Channel Parameters](#channel-parameters)
	* [Frequency Sweep Settings \(Spectroscopy I\)](#frequency-sweep-settings-spectroscopy-i)
	* [Frequency Sweep Settings \(Spectroscopy II\)](#frequency-sweep-settings-spectroscopy-ii)
	* [Amplitude Sweep Settings](#amplitude-sweep-settings)
	* [Modulation Depth Sweep Settings](#modulation-depth-sweep-settings)
6.  [FPGA Control](#fpga-control)
	* [RT FIFO Health](#rt-fifo-health)
	* [RT Status](#rt-status)
7.  [Thresholding Control](#thresholding-control)
8.  [Signal Panel](#signal-panel)



##### Device Settings
![Device Settings](https://raw.githubusercontent.com/modelkits/Dep_App_2024/main/DEP_App/Documentation/Pics/Device%20Settings.png "Device Settings")

Here you can choose your *Signal Generator* device ( **Siglent 2082x** or **Digilent Analog Discovery 2**), set IP adress of your *cRIO* device and set parameters for connection to *Signal Generator* device. *AD2* value should be set to **0**. *Siglent Name* you can set by selecting from availbale options at the combo box (**Siglent 2082X** should be already connected to computer and switched On at this moment). *Reader Endpoint* should be set to **StreamReader** value. After setting these parameters for the first time it's better to set them as default values and save a PC_Main.vi. It will store them for next time.

##### Device Control
![Device Control](https://raw.githubusercontent.com/modelkits/Dep_App_2024/main/DEP_App/Documentation/Pics/Device%20Control.png "Device Control")

Here you can connect and disconnect *Signal Generator* device and signal acquisition device - *FPGA*. After pressing *FPGA* button you will be asked to open and run RT_Main.vi from RT Core folder of the LabVIEW project. When the selected device is successfully connected, the corresponding panel will become active.

##### Experiment's Info and recording settings
![Experiment's Info and recording settings](https://raw.githubusercontent.com/modelkits/Dep_App_2024/main/DEP_App/Documentation/Pics/Experiment's%20Info%20and%20recording%20settings.png "Experiment's Info and recording settings")

Here you can set parameters for saving data streams and activity log. *Experiment folder* control let you set or choose main folder where all recordings data will be saved. *Recording Name* control let you specify the beginning of all recordings filenames for data streams and activity log. By pressing *Save?* button you will start saving of activity log. Recording of each signal data stream if controlled individually by buttons *Record Counts?*, *Record Scattering?*, *Record Output?* and *Record AI2?*. Indicator next to these buttons displays current number of chunks stored for each signal data stream. Duration of each chunk is set in the *Seconds In File* control. Data streams are saved in .TDMS format. Activity log is saving in semicolon delimited .CSV format with column names in the first raw.

##### Signal Generator Settings
![Signal Generator Settings](https://raw.githubusercontent.com/modelkits/Dep_App_2024/main/DEP_App/Documentation/Pics/Signal%20Generator%20Settings.png "Signal Generator Settings")

Here you can setup parameters of control signal and scenario parameters. 

##### Channel Parameters
![Channel Parameters](https://raw.githubusercontent.com/modelkits/Dep_App_2024/main/DEP_App/Documentation/Pics/Channel%20Parameters.png "Channel Parameters")

Here you can setup following parameters of control signal
###### Signal Parameters
* *WaveForm Function* - The standard waveform that you want the signal generator to produce: **Sine**, **Square**, **Triangle**, **DC**, **Pulse**
* *DC Offset (V)* - The DC offset of the standard waveform you want the signal generator to produce: **-5V** - **5V**
* *P2P Amplitude (V)* - The amplitude of the standard waveform you want the signal generator to produce: **0.001V** - **10 V**
* *Frequency (Hz)* - The frequency you want the signal generator to produce: **1 uHz** - **80 MHz**

###### Modulation Paramaeters
* *Waveform* - The internal waveform you want to use to modulate the output signal: **Sine**, **Square**, **Triangle**, **UpRamp**, **DnRamp**, **Noise**
* *Type* - Type of modulation: **Amplitude**, **Frequency**
* *Frequency (Hz)* - The frequency at which you want the instrument to generate the modulating waveform: **1 mHz** - **1 MHz**
* *Depth (%)* - The percentage of full modulation you want to apply to the carrier signal (At 0% depth, the output amplitude equals the carrier signal's amplitude. At 100% depth, the output amplitude equals twice the carrier signal's amplitude.):  **0%** - **120%**

*Channel* button switch ON and OFF output signal for choosed channel.
*Modulation Channel* button switch ON and OFF modulation for choosed channel.

##### Frequency Sweep Settings \(Spectroscopy I\)
![Frequency Sweep Settings \(Spectroscopy I\)](https://raw.githubusercontent.com/modelkits/Dep_App_2024/main/DEP_App/Documentation/Pics/Frequency%20Sweep%20Settings%20\(Spectroscopy%20I\).png "Frequency Sweep Settings \(Spectroscopy I\)")

Here you can setup parameters for Actuation Spectroscopy Scenario I

* *f_start(Hz)* - Start value of the control signal frequency
* *f_end(Hz)* - Finish value of the control signal frequency
* *Number of steps* - Number of the control signal frequencies in the sweep series (including f_start and f_end value): **2** - **Reasonible integer value**
* *Channel* - Channel used as control signal: **Channel 1**, **Channel 2**
* *DC Offset (V)* - The DC offset of the control signal
* *amp (V)* - The amplitude of the control signal
* *Total time(s)* - Total duration of the sweep series
* *Modulation Depth (%)* - The percentage of control signal modulation
* *fc (Hz)* - The frequency of the control signal modulation waveform

For the valid range of parameters please check the [Channel Parameters](#channel-parameters) section.
To test control signal which will be used during *Actuation Spectroscopy I* scenario you can manually switch it ON and OFF by *Start Frequency Sweep I* and *Stop Frequency Sweep I* buttons. Button *Start Frequency Sweep I - smooth* launches sweep series with much less signal distortion between each sweep steps. This mode is also used when running scenario automatically.

##### Frequency Sweep Settings \(Spectroscopy II\)
![Frequency Sweep Settings \(Spectroscopy II\)](https://raw.githubusercontent.com/modelkits/Dep_App_2024/main/DEP_App/Documentation/Pics/Frequency%20Sweep%20Settings%20\(Spectroscopy%20II\).png "Frequency Sweep Settings \(Spectroscopy II\)")

Here you can setup parameters for Actuation Spectroscopy Scenario II

* *f(Hz)* - The control signal frequency
* *f_end(Hz)* - Finish value of the control signal frequency
* *Number of steps* - Number of the control signal frequencies in the sweep series (including fc_start and fc_end value): **2** - **Reasonible integer value**
* *Channel* - Channel used as control signal: **Channel 1**, **Channel 2**
* *DC Offset (V)* - The DC offset of the control signal
* *amp (V)* - The amplitude of the control signal
* *Total time(s)* - Total duration of the sweep series
* *Modulation Depth (%)* - The percentage of control signal modulation
* *fc_start (Hz)* - Start value of the control signal modulation waveform frequency
* *fc_end(Hz)* - Finish value of the control signal modulation waveform frequency

For the valid range of parameters please check the [Channel Parameters](#channel-parameters) section.
To test control signal which will be used during *Actuation Spectroscopy II* scenario you can manually switch it ON and OFF by *Start Frequency Sweep II* and *Stop Frequency Sweep II* buttons. Button *Start Frequency Sweep II - smooth* launches sweep series with much less signal distortion between each sweep steps. This mode is also used when running scenario automatically.


##### Amplitude Sweep Settings
![Amplitude Sweep Settings](https://raw.githubusercontent.com/modelkits/Dep_App_2024/main/DEP_App/Documentation/Pics/Amplitude%20Sweep%20Settings.png "Amplitude Sweep Settings")

Here you can setup parameters for Amplitude Sweep Scenario

* *f(Hz)* - The control signal frequency
* *fc (Hz)* - The frequency of the control signal modulation waveform
* *Number of steps* - Number of the control signal frequencies in the sweep series (including f_start and f_end value): **2** - **Reasonible integer value**
* *Channel* - Channel used as control signal: **Channel 1**, **Channel 2**
* *DC Offset (V)* - The DC offset of the control signal
* *Total time(s)* - Total duration of the sweep series
* *Modulation Depth (%)* - The percentage of control signal modulation
* *amp_start (V)* - Start value of the control signal amplitude
* *amp_end (V)* - Finish value of the control signal amplitude

For the valid range of parameters please check the [Channel Parameters](#channel-parameters) section.
To test control signal which will be used during *Amplitude Sweep* scenario you can manually switch it ON and OFF by *Start Amplitude Sweep* and *Stop Amplitude Sweep* buttons. Button *Start Amplitude Sweep - smooth* launches sweep series with much less signal distortion between each sweep steps. This mode is also used when running scenario automatically.

##### Modulation Depth Sweep Settings
![Modulation Depth Sweep Settings](https://raw.githubusercontent.com/modelkits/Dep_App_2024/main/DEP_App/Documentation/Pics/Modulation%20Depth%20Sweep%20Settings.png "Modulation Depth Sweep Settings")

Here you can setup parameters for Modulation Depth Sweep Scenario

* *f(Hz)* - The control signal frequency
* *fc (Hz)* - The frequency of the control signal modulation waveform
* *Number of steps* - Number of the control signal frequencies in the sweep series (including f_start and f_end value): **2** - **Reasonible integer value**
* *Channel* - Channel used as control signal: **Channel 1**, **Channel 2**
* *DC Offset (V)* - The DC offset of the control signal
* *Total time(s)* - Total duration of the sweep series
* *depth_start (%)* - Start value of the control signal modulation percentage
* *depth_end (%)* - Finish value of the control signal modulation percentage
* *Amplitude (V)* - The amplitude of the control signal

For the valid range of parameters please check the [Channel Parameters](#channel-parameters) section.
To test control signal which will be used during *Modulation Depth Sweep* scenario you can manually switch it ON and OFF by *Start Depth Sweep* and *Stop Depth Sweep* buttons. Button *Start Depth Sweep - smooth* launches sweep series with much less signal distortion between each sweep steps. This mode is also used when running scenario automatically.

##### FPGA Control
![FPGA Control](https://raw.githubusercontent.com/modelkits/Dep_App_2024/main/DEP_App/Documentation/Pics/FPGA%20Control.png "FPGA Control")

Here you can check FPGA status. In operating mode, all LED indicators must be turned off. In case of malfunctions in the FPGA, the corresponding indicator will help diagnose the problem. *Streaming* button is used to turn ON and OFF data streaming from FPGA.

##### RT Status
![RT Status](https://raw.githubusercontent.com/modelkits/Dep_App_2024/main/DEP_App/Documentation/Pics/RT%20Status.png "RT Status")

Here you can check CPU and memory utilization at CompactRio.

##### Thresholding Control
![Thresholding Control](https://raw.githubusercontent.com/modelkits/Dep_App_2024/main/DEP_App/Documentation/Pics/Thresholding%20Control.png "Thresholding Control")

Here you can setup parameters to automatically run different scenarios based on level of **Counts** signal.
* *Average Counts* - shows current level of **Counts** signal
* *RMS Counts* - root mean square values of **Counts** signal
* *Mean per bin* - mean value of **Counts** signal per bin. Bin size value is set on the [Signal Panel](#signal-panel) (at Counts parameters section)
* *Thresholding* - turn ON and OFF automatic scenario launching mode
* *Threshold (counts/s)* - **Counts** value threshold, when exceeded, scenario will be automatically launched
* *Precheck dur. (ms)* - waiting period after exceeding the threshold before scenario launching
* *Scenariod dur. (ms)* - duration of the period after starting the scenario until the control signal is turned OFF. This value should be equal or longer then **total time** value of the coresponding scenario
* *Release dur. (ms)* - duration of the period after control signal switching OFF until switching ON back
* *Threshold control* - while it's ON allows to avoid false scenario launching by checking value of **Counts** signal during *precheck* period. If the value falls below the threshold level, the script will not run
* *Events* - shows the number of successful scenario launches
* *Reset* - reset *Events* value
* *Manual* - launch scenario manually
* *Threshold Scenario* - choose what Scenario will be launched
* *SG/DIO* - set the method of control signal connection. SG - control signal is directly connected, DIO - control signal is connected through additionl switch
* *Threshold Scenario* - choose which scenario will be launched:
	* *Scenario 1 (DIO)* - connect and disconnect control signal via additional switch
	* *Scenario 2 (Spectroscopy I)* - gradual control signal frequency changes according to the values at [Frequency Sweep Settings \(Spectroscopy I\)](#frequency-sweep-settings-spectroscopy-i) panel
	* *Scenario 3 (Spectroscopy II)* - gradual control signal modulation frequency changes according to the values at [Frequency Sweep Settings \(Spectroscopy II\)](#frequency-sweep-settings-spectroscopy-ii) panel
	* *Scenario 4 (Amplitude Sweep)* - gradual control signal amplitude changes according to the values at [Amplitude Sweep Settings](#amplitude-sweep-settings) panel
	* *Scenario 5 (Depth Sweep)* - gradual control signal amodulation depth changes accroding to the values at [Modulation Depth Sweep Settings](#modulation-depth-sweep-settings) panel


##### Signal Panel
![Signal Panel](https://raw.githubusercontent.com/modelkits/Dep_App_2024/main/DEP_App/Documentation/Pics/Signal%20Panel.png "Signal Panel")

Here you can monitor main signals state *Counts*, *Scattering*, and *Output*. Each of them have several controls and indicators
* *Counts*
	* Main chart indicator
	* Frequency spectrum indicator
	* *Display* button switch ON and OFF main chart indicator
	* *Spectra?* button switch ON and OFF frequency spectrum indicator
	* *Seconds in Count Spectra* - sets the time interval for which the frequency spectrum is calculated
	* *Seconds in chart* - sets the duration of the time interval for the main chart indicator
	* *Bin time (ms)* - binnig is used for Counts value calculation. This parameter sets bin window size in milliseconds.
* *Scattering*
	* Main chart indicator
	* Frequency spectrum indicator
	* *Display* button switch ON and OFF main chart indicator
	* *Spectra?* button switch ON and OFF frequency spectrum indicator
	* *Seconds in Spectra* - sets the time interval for which the frequency spectrum is calculated
	* *AI seconds on chart* - sets the duration of the time interval for the main chart indicator
	* *Decimator Analog Input* - downsampling is used for dispalying signal at the main chart. This parameters sets the decimating factor value
	* *Low Pass* - switch ON and OFF low pass filtering of the scattering signal
	* *Cutoff (Hz)* - sets the cutoff frequency value for the low pass filterin
* *Output*
 	* Main chart indicator
 	* Frequency spectrum indicator
 	* *Display* button switch ON and OFF main chart indicator
 	* *Spectra?* button switch ON and OFF frequency spectrum indicator
 	* *Seconds in Spectra* - sets the time interval for which the frequency spectrum is calculated
 	* *AI seconds on chart* - sets the duration of the time interval for the main chart indicator
 	* *Decimator Analog Input* - downsampling is used for dispalying signal at the main chart. This parameters sets the decimating factor value

Also on the right side of the *Signal Panel* there is a block of indicators about current scenario and some statistics of launched scenarios
* *Current Value* - during scenario execution, shows the current value of modified parameter of scenario (frequency, modulation frequency, amplitude or modulation depth)
* *last t* - interval in seconds between last scenario starting time and the moment when the value of *Counts* signal fell below *Threshold* level
* *last par* - value of the modified parameter at above moment
* *All t* - list of all above intervals
* *All par* - list of all above parameters values
* *Mean t* - mean value of the *All t* list
* *mean par* - mean value of the *All par* list
* *Reset* button clears a list of *All t* and *All par*. It is useful when changing the scenario so that the average calculates the same parameter


##### RT FIFO Health
![RT FIFO Health](https://raw.githubusercontent.com/modelkits/Dep_App_2024/main/DEP_App/Documentation/Pics/RT%20FIFO%20Health.png "RT FIFO Health")

This is a control panel of RT_Main.vi from RT Core folder of the LabVIEW project. Here you can check FPGA status. In operating mode, all LED indicators must be turned off. In case of malfunctions in the FPGA, the corresponding indicator will help diagnose the problem.










