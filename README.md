# 3IA Health Data Hub - Workshop on heterogeneous data and Federated Learning


Material for workshop on heterogeneous data and Federated Learning - Winter school - 3IA/Health Data Hub

Site: https://epione.gitlabpages.inria.fr/flhd/

## Add my notebook as part of the workshop

1. Create your talk in the form of a Jupyter notebook (if you have code) or in a markdown file (if you are explaining a subject)
2. Send your notebook(s) by email
3. Ask someone (if you need) to make your notebook available in the site

## Making notebooks available in the website (do it only if you feel capable)
This repository is already configured to generate a GitLab Pages site. To make a notebook available:

1. Be sure to pull before making any changes
2. Copy the notebook into either `federated_learning` or `heterogeneous_data`
3. Edit the `_toc.yml` file adding your notebook to it (**WARNING:** All notebooks must be called in `_toc.yml` otherwise the ci will launch an error).
4. Push your changes to `master`.

Automatically a CI instance will be launched (you can check for it in `CI/CD > Pipelines`). Be sure it passes.
That is it.
