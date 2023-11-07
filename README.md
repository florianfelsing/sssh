# sssh: Simplified SSH for Amazon ECS Fargate

`sssh` is a Bash script designed to streamline the process of using `ecs-exec` to execute commands in Amazon ECS Fargate containers. It provides an interactive experience for selecting ECS profiles, clusters, services, containers, and tasks to run shell commands or port forwarding.

> This is an actively maintained fork of the original `sssh` project. Contributions and feedback are welcome!

## Table of Contents

1. [Prerequisites](#prerequisites)
2. [Installation](#installation)
3. [Usage](#usage)
4. [Contributing](#contributing)
5. [Special Thanks](#special-thanks)
6. [License](#license)

## Prerequisites

- [AWS CLI](https://docs.aws.amazon.com/cli/latest/userguide/getting-started-install.html)
- [Session Manager plugin for the AWS CLI](https://docs.aws.amazon.com/systems-manager/latest/userguide/session-manager-working-with-install-plugin.html)
- [jq](https://stedolan.github.io/jq/download/)
- [peco](https://github.com/peco/peco#installation)

**Note**: Ensure that your AWS CLI session profile is set to output in JSON format before running the script. This is crucial as the script may not function correctly otherwise. You can set the output format to JSON by executing `aws configure sso`.

## Installation

To install `sssh`, clone the repository and run the script as follows:

```bash
git clone https://github.com/your-username/sssh.git
cd sssh
./sssh
```

## Usage

`sssh` simplifies the process of connecting to your Amazon ECS Fargate containers. Here is how you can leverage its functionality:

**Interactive Shell:**

```bash
# Launch an interactive shell within your selected ECS container.
# The script will guide you through a series of prompts to select the appropriate
# AWS profile, cluster, service, container, and task.
  ./sssh
```

**Port Forwarding:**

```bash
# Set up port forwarding from your local machine to a remote service via the
# selected container. You'll need to provide the remote host's address, the
# remote port, and a local port to forward to.
./sssh --remote-host rds.example.com --remote-port 3306 --local-port 13306
```

**Getting Help:**

```bash
# Display the help information for additional context and command usage.
./sssh --help

```

## Contributing

This fork of `sssh` is actively maintained. Contributions are welcome and greatly appreciated! If you have a feature request, a bug to report, or a patch that you would like to contribute, please feel free to raise an issue or open a pull request. We aim to foster an inclusive and welcoming community around improving and extending this tool.

## Special Thanks

Special thanks to the authors and original contributors:

- [leewc](https://github.com/leewc)
- [bamkuhen](https://github.com/bamkuhen)
- [yuki777](https://github.com/pj8/sssh)

## License

This project is a fork of [sssh](https://github.com/yuki777/sssh) originally created by Yuki Adachi. It is licensed under the Apache License, Version 2.0. This fork is being actively maintained and may include modifications not present in the original repository. For details on changes made, please see the commit history.
