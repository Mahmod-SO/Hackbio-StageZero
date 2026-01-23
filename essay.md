**Reproducible Figures Are More Valuable Than Fancy Figures**

**The Primacy of Reproducibility in Bioinformatics**

In modern bioinformatics, figures are not mere illustrations but distilled evidence of data analysis. Every plot should be reproducible by code, not a one-off crafted in a graphical editor. A manually polished chart may look impressive, but if it cannot be regenerated from the source data, its scientific value is compromised. We contend that in research and especially in bioinformatics, reproducibility must take precedence over aesthetic flourish. When every aspect of a figure is produced by script, the link between raw data and final graphic remains transparent, enabling verification and reuse.

**The Pitfalls of Manual Figure Design**

Manually designed figures introduce risk and opacity. Each adjustment made by hand (in Illustrator, PowerPoint, or similar) severs the connection to the data pipeline. Copying points, dragging chart elements, or tweaking fonts by eye are actions that cannot be captured in code. This makes it impossible for a peer or auditor to retrace how a figure was generated. The process is simply too prone to errors. A simple misalignment or mislabeled axis can go unnoticed when graphs are edited by hand. Updating such a figure is quite tasking and any change in the data requires repeating all manual edits. In effect, a fancy figure may hide undocumented steps and prevent others from confirming that it was produced correctly.

**Advantages of Script‑Driven Figures**

Scripted figure generation (for example, using R/ggplot2 or Python/matplotlib) offers multiple benefits over manual design:

- **Automatic regeneration**: When data or parameters change, the figure can be updated by rerunning the script. There is no need to redo work by hand.
- **Full transparency**: Every data point, axis label, and visual element is defined in code. Others can inspect the script to understand exactly how the plot was made.
- **Consistency and style control**: A single script can produce multiple related figures with uniform styling (colors, fonts, scales) without repetitive manual formatting. Themes or templates ensure a coherent look across all outputs.
- **Collaboration and versioning**: Code can be stored in version control (Git), so multiple researchers share the same script. Team members can branch, modify, and merge changes, ensuring that everyone works from the same baseline.

These advantages translate into clear wins in bioinformatics projects. For instance, if a new sample is added to a sequencing experiment or a parameter in the analysis is tweaked, the existing figure scripts immediately generate updated plots. Scripted plots also handle large or complex data sets more reliably than manual methods. Finally, code-driven figures can embed metadata (like software versions or parameter values) in the document, further aiding reproducibility.

**Peer Review, Auditing, and Regulatory Context**

Reproducible figures are crucial for peer review and regulatory science workflows. Reviewers increasingly expect access to the code behind a paper's results. A script that generates each figure allows a reviewer to run it and verify the output quickly. If the figure were only provided as a static image, reviewers must take the authors' word for accuracy. In practice, journal policies on code and data sharing are becoming stricter: providing figure‑generation scripts demonstrates rigor and proof of authenticity, especially as AI written papers and plagiarism is now on the rise.

In regulated contexts (such as clinical genomics or drug development studies), reproducibility is mandatory. Auditors or regulators will examine the data analysis pipeline step by step. When figures are produced by code, the entire process has a clear audit trail. For example, a regulatory submission might require that every plot be reproducible from the submitted data and scripts. Scripted figures make it straightforward to demonstrate compliance with good laboratory and data standards. In contrast, hand edited graphics would raise red flags in an audit: without code, there is no way to prove that the figure truly reflects the underlying results.

**Tools and Workflows for Reproducible Figure Generation**

A range of tools makes code-driven figures practical and even straightforward:

- **R with RMarkdown or Quarto**: These literate programming tools combine narrative text and R code. Using packages like ggplot2, a researcher can write a few lines of code to generate a publication‑quality graphic. Knitting the document produces figures automatically. The result is a self‑contained report where every figure comes from a script that can be rerun.
- **Python with Jupyter Notebooks**: Jupyter allows Python (or R, Julia, etc.) code and output to coexist in one document. Plots created with matplotlib or seaborn can be generated inline. Colleagues can rerun cells to regenerate figures. Notebooks support parameterization (via widgets or parameters) to explore different inputs, and with tools like Papermill they can be rerun end to end.
- **Workflow managers (Snakemake, Nextflow, Make)**: These tools treat figure files as targets in an analysis pipeline. A rule specifies how to generate each figure from raw data and scripts. The workflow system tracks dependencies, automatically rebuilding figures when inputs change. This ensures that no step is missed and provides an audit trail from raw data to final images.
- **Version control and containers**: Storing figure scripts (and data) in Git ensures a history of changes. Combining this with containerized environments (Docker, Singularity) freezes the computing context. Others can clone the repository, start the container, and rerun the code to reproduce every plot identically.

Using these workflows, a bioinformatics team or a bioinformatician can achieve both reproducibility and high visual quality. For example, ggplot2 supports extensive theming and annotation, so aesthetic refinements are done in code (not by hand), preserving reproducibility. Automated tools like Patchwork (for ggplot) or matplotlib's subplots can assemble multi-panel figures programmatically. The overhead of learning these tools is quickly offset by the time saved during revisions and by increased confidence in the results.

**Examples from Bioinformatics**

Reproducible figure practices are already paying dividends in bioinformatics. For example, in many genome analysis projects, quality-control plots (coverage histograms, PCA of samples, etc.) are generated by scripts as part of the pipeline. If a sample is dropped or reprocessed, rerunning the script updates all QC figures in one step. Another case is when a multi-institution RNA‑Seq study needed an extra heatmap after peer review, the team simply ran their existing R script with a new parameter. The figure appeared immediately, consistent with the rest of the paper.

Similarly, during an internal audit at a cancer genomics lab, auditors asked for the code behind a Kaplan-Meier survival curve in a publication. Because the lab had used an RMarkdown document, they provided the R script and raw data. The auditor reran the code and matched the published curve point for point. Had the figure been manually drawn, this level of verification would have been impossible without redoing the entire analysis from scratch. These examples show how scripted figures streamline collaboration and quality control: co-authors or auditors can inspect and adapt the code, ensuring that every image is a true, updatable representation of the data.

In conclusion, while practicing bioinformatics, data science or any field that requires data and/or research, visual polish should never come at the expense of reproducibility. A beautiful figure that can't be regenerated by others is of limited scientific use. Conversely, a reproducible figure is fundamentally more valuable as it can be verified, updated, and extended. We urge researchers to treat figures as code artifacts. By embracing tools like RMarkdown, Jupyter, and workflow managers, bioinformaticians can achieve both clarity of presentation and fidelity to data. In the end, a reproducible figure earns trust while a merely fancy figure does not.