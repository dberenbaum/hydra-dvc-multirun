Example of running multiple configurations in one command using Hydra:

```
$ dvc exp run --queue -S group=one,two
Queueing with overrides '{'params.yaml': ['group=one']}'.
Queued experiment '634a8fa' for future execution.
Queueing with overrides '{'params.yaml': ['group=two']}'.
Queued experiment '0c283dc' for future execution.

$ dvc exp run --run-all
Following logs for all queued experiments. Use Ctrl+C to stop following logs (experiment execution will continue).

Running stage 'test':
> cat params.yaml
group:
  a: 1
  b: 1
Updating lock file 'dvc.lock'

To track the changes with git, run:

        git add params.yaml dvc.lock dvc.yaml

To enable auto staging, run:

        dvc config core.autostage true
Running stage 'test':
> cat params.yaml
group:
  a: 2
  b: 2
Updating lock file 'dvc.lock'

To track the changes with git, run:

        git add params.yaml dvc.yaml dvc.lock

To enable auto staging, run:

        dvc config core.autostage true

Ran experiment(s): exp-38627, exp-8812f
To apply the results of an experiment to your workspace run:

        dvc exp apply <exp>

To promote an experiment to a Git branch run:

        dvc exp branch <exp> <branch>
```
