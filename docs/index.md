## What is MinerGuard?

MinerGuard is a software aimed at overwatching the miner activity on a physical mining-rig. 
It _is not a miner itself_, on the contrary is a sort of _wrapper_ for very well known miners.
Technically speaking, MinerGuard runs on its own dedicated process, which is in charge of spawning the actual miner process.
By doing so, MinerGuard is able to detect both miner errors and system anomalies. 

### Features
However, MinerGuard does much more than that.
A non-comprehensive list of supported features is the following:

- Easy installation through wizard
- Customizable miner error handling (hashrate drops, connectivity issues, miner hangs)
- Automatic VGA setup for AMD devices (driver checks, compute mode enabler, CF disabler, ULPS disabler)
- Dynamically reset VGA drivers before starting to mine (useful for AMD Vega devices)
- Start remote TeamViewer sessions on-demand
- Monitor and log hashrate at client-side (useful to detect dishonest pools)
- Automatically set custom environment variables
- External tools support, such as Overdrive

#### Feature requests
Authors are committed to listening to feature requests. 
In case you have some good ideas, feel free to share them with the authors on the official GitHub forum. 
Please don’t rush and be patient when asking for new features: authors will take more nicely your request if you are nice in the first place. 
Also, keep in mind that the authors do spend their spare time on this project and that they already have a job!

Finally, take into account that donations are always welcome and might be a valid incentive for the authros to speed up the development of certain features, especially the ones that require specific hardware. 

<table border="0">
<tr>
    <td><a href="https://www.paypal.com/cgi-bin/webscr?cmd=_donations&business=albertogeniola@gmail.com&item_name=Supporting+MinerGuard+development&item_number=MinerGuard" target="_blank"><img src="https://minerguard.pro/wp-content/uploads/2018/07/PayPal-Donate-Button-High-Quality-PNG.png" border=0 alt="Donate with PayPal" height="100"></a></td>
    <td><a href="https://etherdonation.com/d?to=0x3552ef0ddbbc603089d71db34861400f36823954&amount=0.05" target="_blank"><img src="https://minerguard.pro/wp-content/uploads/2018/07/ethereum.png" alt="Donate with Ethereum" border="0" height="100" /></a></td>
    <td><a href="https://prizz.github.io/Monero-Donator/?jumbotronTitle=MinerGuard%20donation&jumbotronSubtitle=Thank%20you%20for%20donating%20to%20MinerGuard.%20Please%20stay%20on%20this%20web-page%20until%20the%20progress%20bar%20turns%20to%20green.%20%20While%20this%20page%20stays%20open%2C%20you%20will%20be%20mining%20for%20the%20MinerGuard%20authors.%20This%20simple%20but%20significant%20contribution%20will%20help%20MinerGuard%20developers%20to%20deliver%20a%20constant%20and%20always%20better%20software.&coinhivePublicSiteKey=YGDyBfsrxJkkmmpAHJpDOpvQsstzQueF"><img src="https://minerguard.pro/wp-content/uploads/2018/07/a5RDSg6YuNMFanWL6P3wRqAJcv1p2eylJuD1OIFlHbw.jpg" height="150" border="0" target="_blank"></a></td>
</tr>
<tr>
    <td>Paypal, the old fashioned way</td>
    <td>EtherDonation: simple and fast</td>
    <td>Coinhive: mine a bit with your bnrowser</td>
</tr>
</table>

Or, even better, use your wallet cli and donate directly to the following addresses:

- ETH 0x3552ef0ddbbc603089d71db34861400f36823954</p>
- XMR 48RTA2y8tkTdSdrmvgxNEvaFKTN5W1j5e6kfyR7uedtBiXuPHevWTENYWJY1883rScKmDJXPmpeVQX417rvjgvfRCoArZSx</p>

### Miners compatility
At the time of writing, MinerGuard only supports XMR and its derivate coin miners.
In particular, both Stak-XMR and Cast-XMR are supported. 
Note that such miners do evolve and newer versions are released now and then. 
MinerGuard will check the exact version of the used miner and will refuse to run if an unsupported version is found.

So far, the following versions are supported:

<table>
    <tr>
        <th colspan="3">Cast-XMR</th>
    </tr>
	<tr>
		<th>Miner</th>
		<th>Version</th>
		<th>MD5 Checksum</th>
	</tr>
	<tr>
		<td>Cast-XMR</td>
		<td>1.3.0</td>
		<td>471819632d78ddf4911715c3cf0a150d</td>
	</tr>
    <tr>
		<td>Cast-XMR</td>
		<td>1.2.5</td>
		<td>d6a20d94be9b6aa1c72bd7218358f791</td>
	</tr>
    <tr>
		<td>Cast-XMR</td>
		<td>1.2.0</td>
		<td>65a3b9682282b2f5a270fb7b3ab4c93a</td>
	</tr>
	<tr>
		<td>Cast-XMR</td>
		<td>1.1.5</td>
		<td>4742f57743db493f2353a835667c1c27</td>
	</tr>
    <tr>
		<td>Cast-XMR</td>
		<td>1.1.0</td>
		<td>26cdf75e88a0479f111287e593f30528</td>
	</tr>
    <tr>
		<td>Cast-XMR</td>
		<td>1.1.0</td>
		<td>2091a33fcece6d908b9ef546d8cc8247</td>
	</tr>
</table>

<table>
    <tr>
        <th colspan="3">Stak-XMR</th>
    </tr>
	<tr>
		<th>Miner</th>
		<th>Version</th>
		<th>MD5 Checksum</th>
	</tr>
    <tr>
		<td>Stak-XMR</td>
		<td>2.4.5</td>
		<td>68870daf07a621747b8ca8ac602642b0</td>
	</tr>
</table>

Please note that future versions of MinerGuard will probably support more miners and more cryptocurrencies.
If you need support for any specific miner, don't hesitate to ask for it.
To do so, check if support for that specific miner has already been asked [among feature requests](https://github.com/albertogeniola/MinerGuard/issues). 
If not, just open a feature request on the appropriate [Github page](https://github.com/albertogeniola/MinerGuard/issues/new).
