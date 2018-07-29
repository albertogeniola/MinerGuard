## Configuring MinerGuard
Once you start MinerGuard, you should receive an error complaining about missing or bad configuration. 
_Don't warry_, that's normal. 

> Experts users might notice that the configuration file is in JSON format and is stored in the installation path.

The recommanded way for handling MinerGuard configuration is to use the MinerGuard user interface. 
From the _Configuration_ menu, select _Edit_. 
A new dialog will apper. 
Each tab of the new window takes care of configuring a specific part of MinerGuard.
So, let's have a look at each one.


### General
This section contains the general configuration options that are valid for the miner-rig itself. 

![General configuration screenshot](https://minerguard.pro/wp-content/uploads/2018/07/general.png)

**Miner identifier**: 
the name to assign to this miner. 
In case you have multiple miners, be sure to assign each one a distinct (possibly meaninful) name. 
Such id is used to uniquely identify the miner when issuing remote commands. 

**Autostart at windows boot**: 
when enabled, MinerGuard will automatically start at Windows boot. 
Be advised: enabling this option requires you to set up an account with administrative rights that logs automatically on the system.
The wizard procedure to do so will appear when you save the configuration.

**Ensure Windows update off**: 
when enabled, this option will make sure windows updates are switched off.
This is particularly useful to make sure that the system does not update drivers on its own.
Please note that this option will not prevent AMD/nVIDIA dirvers from automatically update.
Please make sure drivers are set to avoid automatic updates.

**Mining software**:
the mining software to be used. 
You might chose one of the supported miners at a time. 

**Autostart mining**:
start mining as soon as MinerGuard is opened. 
This option is particularly useful when also MinerGuard is configured to startup automatically at windows boot (i.e. _autostart at windows boot_)

**Pool**: 
full address of mining pool to be used (including the port).
The address should be in a form understandable to the chosen miner. 
For instance, _pool.supportxmr.com:7777_ is a valid entry for this input.

**Wallet**: 
surely, the most important setting. 
Put in here your full wallet address.

**Password**: 
optional. If requested by the pool, put in here your password. 

**Environment Variables**:
specify in this table which are the environment variables to be set, before starting the miner.
For instance, Stak-XMR used to require "GPU_MAX_ALLOC_PERCENT=100".
To do so, just put _GPU_MAX_ALLOC_PERCENT_ in the first column and _100_ in the same row, on the second column.

### Error Handling
This section configures the automatic error-recovery policies that MinerGuard will apply in case of errors.

![Error handling screenshot](https://minerguard.pro/wp-content/uploads/2018/07/error_handling.png)

**Hashrate check interval**: 
how frequently MinerGuard will check the hashrate of the miner and will react in case the hashrate is less than the threshold.
This value is expressed in seconds. 
A value of 0 disables the hashrate check. 
Don't put values too strict here: a value of 120 is good enough.

**Minimum hashrate threshold**: 
the hashrate threshold under which the miner should be restarted. 
This value really depends on your hardware. 
A value of 0 disables the check.
In case you have 1 Vega56 and you are mining with Cast-XMR and with blockchain drivers, you might consider 1500 as a good value.
Don't put a value that is too close to your best hashrate, instead put something less: let's say that 300 H/s less per card is good threshold.

**Max miner restarts per hour**:
how many times, at most, MinerGuard should try to restart the miner in case the hashrate drops of if there are errors in general.

**What to do when maximum restart reached**:
what to do when the maximum number of miner restart is reached. 

> Let's make a practical example here.
Assume you specify a hashrate interval of 60, a minimum hashrate of 2000 and 3 as maximum number of restarts per hour.
MinerGuard will calculate the hashrate average every minute of hashing. 
If the hashrate drops under 2000 hashes per seconds, the MinerGuard will restart the miner.
If this happens for more than 3 times in an hour, then the miner will _halt and wait_.


### VGA Settings
The VGA section deals about generic features that apply to any graphic card installed to the system.
Some VGA settings specific to their model/brand are instead available on the next sections.

![VGA Settings](https://minerguard.pro/wp-content/uploads/2018/07/vga_settings.png)

**Auto reset VGAs**:
whether to reset certain graphics card before mining start/restart. 
When this option is active, is applies only to graphic cards that match the Plug-n-play identifiers inputted in the bow below.

**PNP IDS to reset**:
the device Plug-n-play IDs matching VGA cards to be reset before starting the mining software.
To add a card type to the list of cards to be automatically restarted, just double click on the corresponding VGA from the list below.

>You probably don't need to use this feature, unless you are using some unstable driver.
>For instance, people using BlockChain drivers with Vega devices, might really take advantage from this option.


### AMD Settings
Here you find the configuration options specifically for AMD graphics adapters.

![AMD Settings](https://minerguard.pro/wp-content/uploads/2018/07/vga_settings.png)

**Auto enable compute mode**: 
whether to ensure compute mode is switched on for all the AMD devices in the system.
When this option is enabled (_default_), MinerGuard will ensure that the AMD driver is in compute mode.
Please note that compute mode availability strictly depends on the driver version installed on the system.
Compute mode is particularly effective for Radeon RX 400 and 500 series. 
This option also affect Vega cards, enabling large page support.

**Disable Crossfire**:
when enabled (_default_), MinerGuard will disable the Crossfire funcionality for all detected AMD cards.
When mining, it is strongly suggested to disabled CF.

**Disable ULPS**:
when checked (_default_), MinerGuard disables ULPS functionality for AMD cards. 
Again, for best mining performance, ULPS should be disabled.

**Ensure Driver Version**:
when true, MinerGuard checks if the driver version of the AMD devices matches one of the drivers listed below.
If this does not happen, user is notified about the error.

**Allowed Driver Versions**:
list of whitelisted driver versions to be checked by the "Ensure Driver Version" option.

>Two words about driver version enforcement.
>This option is useful when the system still has Windows Updates enabled.
>In fact, Windows might suddenly update the VGA cards driver without user's approval.
>If this check is enabled, MinerGuard will detect the different installed driver version and will notify the user about the anomaly.

### External Tools
In this section you will find the options to configure some external tools.

![External tool screenshot](https://minerguard.pro/wp-content/uploads/2018/07/external_tools.png)

**Use Overdriventool**:
whether to run Overdriventool before starting to mine. 
Overdriventool is a software that enables P-states for AMD cards. 
It is particularly useful when running VEGAs / RX500 cards without custom bios / Soft-Tables.

**Overdriventool path**:
the location on the system where to find the Overdriventool executable.

**Overdriventool command-line**:
arguments to pass to overdriventool software. 

**Abort on overdriventool failure**:
when this option is enabled, any error of Overdriventool will cause the miner to halt. 
This might be ok if mining without optimized P-states is unprofitable. 
However, if mining without P-States enabled is ok, you should not halt the miner if overdriventool fails.

>Please note that Overdriventool profiles file must reside next to the overdriventool executable, i.e. both of them must be in the same directory.

### Cast-XMR
This section shows configuration options for the Cast-XMR miner.

![Cast-XMR screenshot](https://minerguard.pro/wp-content/uploads/2018/07/cast_xmr.png)

**Additional command line**:
any specific command line option to pass to the miner. 
Note that basic options such as pool-address, username, password are already automatically handled by MinerGuard itself.
Usually, you don't need to specify anything in this field.

**Cast XMR Path**:
full path to the Cast-XMR executable. 

**Daemon Port**:
port to pass to the miner for spawning the local viewonly http-server used to monitor its status and hashrate.
Generally, port 7777 is a good option. 
Please be sure to specify a valid port here, otherwise MinerGuard won't be able to monitor the miner hashrate.

**Log file path**:
full path to the miner-log. 
Useful for troubleshooting procedures in case the miner hangs and MinerGuard is unable to recover.

### Stak-XMR
This section shows configuration options for the Stak-XMR miner.

![Stak-XMR screenhost](https://minerguard.pro/wp-content/uploads/2018/07/Stak-XMR.png)

**Directory of XMR-Stak**:
path to the directory containing XMR-Stak executable and dll.

**Disable CPU mining**:
when true, disables the mining option for the CPU. 
This is usually advisable when the RIG is equipped with several graphic cards and CPU is left free.
Anyways, since MinerGuard makes use of CPU, it's better to disable cpu mining if not strictly needed.

**Disable AMD/NVIDIA mining**:
similarly to the previous option, when enabled, the gpu mining will be disabled.
It is usually ok to leave both AMD and NVIDIA mining enabled. 
However, if your rig is built with both AMD and nVIDIA cards and you wish to use only AMD cards you can disable the NVIDIA GPU for mining (or vice versa).

**Daemon Port**:
port to pass to the miner for spawning the local viewonly http-server used to monitor its status and hashrate.
Generally, port 7777 is a good option. 
Please be sure to specify a valid port here, otherwise MinerGuard won't be able to monitor the miner hashrate.

**Log file**:
full path to the miner-log. 
Useful for troubleshooting procedures in case the miner hangs and MinerGuard is unable to recover.

**Cryptocurrency to mine**:
which version of the cryupto-currency to mine. 

### Slack
This part of the MinerGuard configuration is dedicated at the notification system.
At the moment, the only supported one is Slack. 
Before configuring Slack, you should read the __Slack and Chatbots section__.

The very first step is to register to Slack website. 
To do so, visit https://slack.com/get-started and select *create a new workspace*.
Complete the registration procedure (don't forget to verify your email account), and make sure to remeber both your workspace name and registration email address.

![Slack screenshot](https://minerguard.pro/wp-content/uploads/2018/07/slack-1.png)

Once you got access to the slack workpspace, get back to the Slack configuration tab and click on _Get-Token_ button.

![Slack screenshot 1](https://minerguard.pro/wp-content/uploads/2018/07/slack2.png)

A new form will appear. 
There, you should click on _Add to Slack_. 
This operation will open the default browser on the system, poiting to Slack permission consent dialog.

![Slack consent screen screenshot](https://minerguard.pro/wp-content/uploads/2018/07/Slack3.png)

From the Slack authorization page, click on _Authorize_.
If everything goes well, the browser will tell you that the operation has been completed and that you can now close the window.
If that happens, it also means that the SlackAccessToken field has been populated with the appropriate value. Therefore, _congrats, you made it!_



