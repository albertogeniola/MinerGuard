## Slack and ChatBots commands
Slack is a collaboration framework, which is free for a number of basic use-cases, which include the ones that we will be using.
In two words, Slack is a messaging system, based on projects.
An user can join one or more projects. 
Each project is composed by a number of *channels*: usually, each channel refers to a particular aspect of the project.

Slack is awesome for a number of features, especially because it supports *chatbot*. 
A chatbot is an automated system that talks to the user, in a human-like way.

*So, how do we use slack?*
In our case, we will use Slack for creating a project and register a chatbot for each rig we are using.
Imagine: each rig that is managed by MinerGuard will join the Slack channel "all-miners". 
Then, you can talk to each of them, addressing each miner with the **identifier** specified in the *general configuration tab*.

### Chatbot commands
There are two different types of commands you can issue to the SlackChat: 
- Single-Miner command
- All-Miners command

As you can imagine, *single-miner* commands are referred to a single miner, while *all-miners* commands are impacting on all miners.
Being directed to a specific miner, every *single-miner* command also requires the miner-id to talk to. 
On the contrary, *all-miners* commands do not need that, because the command will be sent over all the registered miners.

#### Single-Miner commands
##### Getting the status of a specific miner. 
It also provides its current hashrate.

    Status of <MINER-ID>

or

    What's <Miner-ID> status?

##### Starting/Stopping miners

    Start <MINER-ID>

or

    Please run <MINER-ID>

Obviously, you can stop a miner too:

    Stop <MINER-ID>

You might also restart mining in a single command:

    Restart <MINER-ID>

##### Remote control
Interestingly, you can request the miner to start an instance of TeamViewer and to tell you the login credentials to remote access the machine:

    Control <MINER-ID>

or

    Let me remote control <MINER-ID>

#### All-Miners commands
At the moment, the only supported commands that impacts on all miners are "hello" and "status" commands.
The *hello* command will make all the miners respond with their IDs, so that the user will know how many of them are online and what are their names.

    Hello!

The *status* command will do quite the same, but miners will also report their current status and hashrate (so the output on the chat will be more verbose)

    Info

#### Future improvements
Since Slack and chatbots are very nice technologies that simplify asset management, authros will further improve the chatbot so that it can uderstand many more commands.
If you have any idea or requirements, you [should post open a feature request](https://github.com/albertogeniola/minerguard/issues).