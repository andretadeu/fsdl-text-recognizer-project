# Setup

## 1. Sign up for W&B

- Go to https://app.wandb.ai
- Click 'sign up'
- Sign up with Github (or another if you prefer)
- Select whatever username you want

## 1.1. If you cannot use W&B (AWS version)

- Create an AWS account
- Start an EC2 instance with the following characteristics:
  - Instance type: p2.xlarge
  - AMI ID: ami-0027dfad6168539c7
- Access the EC2 instance through SSH: ssh -i <AWS SSH key> -L 8888:127.0.0.1:8888 ubuntu@<EC2 DNS or IP>
- Execute the command: source activate tensorflow_p36
- Create a workspace folder and clone the project inside:

```{sh}
mkdir workspace
cd workspace
git clone https://github.com/full-stack-deep-learning/fsdl-text-recognizer-project.git
```

- After that, go inside the repository folder and run some pipenv commands:

```{sh}
cd fsdl-text-recognizer-project/
pipenv install --dev
pipenv run pip install environment_kernels ipyparallel
```

## 2. Setup a JupyterLab instance

- Go to https://app.wandb.ai/profile
- Enter the code we will share with you at the session into Access Code field.
- You should be dropped into a JuypyterLab instance with 2 GPUs to use for labs.

*From now on, do everything else in that instance*

## 3. Check out the repo

You should already have the repo in your home directory. Go into it and make sure you have the latest.

```sh
cd fsdl-text-recognizer-project
git pull origin master
```

If not, open a shell in your JupyterLab instance and run

```sh
git clone https://github.com/gradescope/fsdl-text-recognizer-project.git
cd fsdl-text-recognizer-project
```

## 4. Set up the Python environment

Run

```sh
pipenv sync --dev
```

From now on, precede commands with `pipenv run` to make sure they use the correct
environment.

## 5. Kick off a command

Before we get started, please run a command that will take a little bit of time to execute.

```sh
git pull
cd lab1/
pipenv run python text_recognizer/datasets/emnist_dataset.py
cd ..
```

# Ready

Now you should be setup for the labs. The instructions for each lab are in readme files in their folders.

You will notice that there are solutions for all the labs right here in the repo, too.
If you get stuck, you are welcome to take a look!