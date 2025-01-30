This is the repository for I320D: Open Source Software Development.

See full syllabus for the course: https://howisonlab.github.io/open_source_software_course/oss_syllabus.html

The course is a fork of a masters course called, "Peer Production".  You can see the [full syllabus for Peer Production](https://jameshowison.github.io/peer_production_course/pp_syllabus.html) to get an overview.

The undergraduate version, currently being developed, will be similar in many ways:

1. The emphasis on learning git and github collaboration
2. The overall sociotechnical approach where technical skills are matched with readings about underlying concepts (e.g., as we learn git collaboration we will read about collaboration theory from organization science, as we read open source licenses we will read about copyright law and cases).

And differ in a few ways:

1. Projects will not be ethnographic participation, they will be data analysis of records left by open source projects.  These might be language analyses or correlations/regressions using summaries of activity in github repositories.
2. The scope will be tighter on open source, rather than wikipedia or creative commons.
3. Students will not be required to locate and describe adaptations of peer production.
4. We will learn about packaging of software (e.g., pip and CRAN).
5. Added material on security implications and management of open source as "procurement risk".

So as the course is being developed, reference the peer production syllabus and repository, but keep the points above in mind.

The course will be useful for those that want to work in data science roles, but also help understand how open source software works and how it has changed the world of software and beyond. 

# Creating the site using quarto

The `quarto` executable is installed via `brew` (so I'm not using the Rstudio bundled version). https://formulae.brew.sh/cask/quarto

Source for the site is in `~/quarto_course` and HTML output goes into `~/docs/current`.  Github pages just sees the compiled html in `docs`.

Currently the workflow for creating the site is this:

1. In Rstudio Termina run `quarto preview quarto_course/` This watches the files and recomplies as needed, showing a live preview in a local browser window.
1. Edit qmd files in Rstudio (including adding any new chapters to `~/quarto_course/_quarto.yml`)
2. Once ready to release, compile the site using Rstudio Terminal commandline `quarto render quarto_course/` (and the _quarto.yml file defines the output directory).
3. Use `git add quarto_course/ docs/` to pickup changes, then commit and push.

It would be possible to use a GitHub action to generate the site, thus only needing to push up the qmd and image files. But since I have to generate locally to preview anyway, that doesn't seem necessary.
