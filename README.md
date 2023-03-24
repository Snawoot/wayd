WAYD
====

What Are You Doing? - sampling profiler for human activity.

It is a tool to estimate shares of time you spend for various activities without invasive data collection or extensive journaling.

The idea is very simple. Program asks user from time to time (e.g. few times a day) what user is doing now. User is expected to provide short answer like "coding", "doomscrolling", "IM/work" or "IM/chitchat". It's fine to not provide response when you're away. Program waits response for a limited amount of time (30 seconds by default).

Once enough datapoints collected, it is possible to approximately calculate share of time spent to each activity: the share is proportional to number of occurences of some activity in the dataset.

Data is sampled with exponentially distributed random intervals. That makes probes quite fair: not skewed by periodical schedule and not anticipated by user so it doesn't influences user's behavior.

For now the only target platform is Linux, but probably it will also work on macOS.

## Installing

Just put script somewhere and make sure either `zenity` or `kdialog` is available in the system.

See [deploy](deploy) directory for useful deployment templates.

## Usage

Just run the script. Collected probes will be available in CSV file located at `~/.wayd/log.csv` by default.

## Settings

Following environment variables are recognized:

| Variable     | Default value         | Description                            |
| ------------ | --------------------- | -------------------------------------- |
| NO\_RESPONSE | `no response`         | Initial response value in the textbox  |
| AVG\_SLEEP   | `10800`               | Average sleep duration in seconds      |
| LOGFILE      | `$HOME/.wayd/log.csv` | Destination file for collected samples |
