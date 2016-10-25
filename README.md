# Stelligent Mini-Project

## Required Mini-Project Scope

1. Write code in a programming language (or languages, configuration management platforms, etc.) of your choice that provisions an environment running on the Linux or Windows operating system (You can choose any supported version of Linux or Windows). The infrastructure code only needs to provision the environment resources and configure a web server. The home page should display a static HTML page with the words: “Automation for the People”1. There should be a single command that launches this environment.
2. Commit all code to a public version­control repository of your choice (e.g. Github) and provide usage instructions.
EXTRA: Write automated infrastructure tests to verify the environment works as expected

## Solution Description

The solution utilzes the AWS CLI and a single CloudFormation template to provision and manage the required web server.

Three bash scripts are provided to run, stop and check status of the web server. All bash scripts verify installation
of the AWS CLI. To permit multiple stack instances to be run concurrently, each bash script accepts an optional [stackname].
If the optional [stackname] is not provided, the default stack name is Stelligent.

* template.json      : CloudFormation Template defining a t1.micro Linux environment with a simple PHP web server

* run_mini_project   : bash helper script to create stack using template.json
                       users may also manually create the stack with a single aws cloudformation create-stack instruction

    Usage : ./run_mini_project [stackname]

* stop_mini_project  : bash helper script to delete stack
                       users may also manually delete the stack with a single aws cloudformation delete-stack instruction

   Usage : ./run_mini_project [stackname]

* check_mini_project : bash script to display status of stack and verify web server displays Automation for the People
		       users may also continuously monitor status  (e.g. watch -n 10 ./check_mini_project [stackname])

   Usage:  ./check_mini_project [stackname]

## Installation

The Stelligent mini-project solution installs in a single directory

    git clone https://github.com/ckoons/stelligent_mini_project.git

