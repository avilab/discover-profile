# Discover virome snakemake profile
This profile configures snakemake to run discover virome workflow in slurm (tested) cluster system. 
Discover-profile profile is based on generic [Snakemake-Profile](https://github.com/Snakemake-Profiles/generic) and in princible can be used also on lsf and pbs cluster system. 
The mapping between snakemake ressources and cluster submission can be configured in the cluster_spec.yaml. 
Default values are used for all rules not having the snakemake ressource paremeters.

The units are minutes and GB but can be changed.

## Deploy profile
To deploy this profile,

```
mkdir -p ~/.config/snakemake
cd ~/.config/snakemake
git clone git@github.com:avilab/discover-profile.git
```

Then, you can run Snakemake with

```
snakemake --profile discover-profile ...
```

so that jobs are submitted to the cluster. If a job fails, you will find the "external jobid" in the Snakemake error message. 
You can investigate the job via this ID. 
Checking slurm status (slurm_status.py) is currently commented off in config.yaml.

