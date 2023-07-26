# Intensity Modulated Radiation Therapy: Advanced-Optimization-Model

## OVERVIEW

Radiation therapy is an effective cancer treatment because high doses of radiation can kill or inhibit the growth of cancer cells more efficiently than normal cells due to differences in repair mechanisms. Recent advances in imaging (CT and MRI) allow accurate visualization of tumor regions. Intensity modulated radiation therapy and tomotherapy enable precise delivery of radiation from different angles to the target area, maximizing the dose to the tumor. In conventional radiotherapy, only a small number of beamlets are used, making it challenging to optimize radiation delivery manually for complex cases. An automated optimization process is now needed to determine the optimal beam angles and intensities, allowing for a much larger number of beamlets to be used and enhancing the treatment's effectiveness while minimizing damage to critical areas surrounding the tumor.

## PROBLEM AT HAND

The radiotherapy oncologists have provided us with sample 2D images of the tumorous and critical areas, along with a set of possible beamlet origins and angles. Each provided image has been transformed into a binary matrix where each element of the matrix corresponds to a pixel in the original image, where a 1 entry indicates the presence of the attribute shown in the image. For example, the binary matrix that corresponds to the tumor area will have a 1 entry if a tumor was present at the corresponding pixel and 0 otherwise.

The beamlet data has been converted to a set of relative intensity matrices, where each matrix corresponds to the relative intensity delivered by a particular beam, normalized between 0 and 1 inclusively. This is the data that captures the variation in intensity of radiation as the beam passes through a region and also the imprecision in a particular beam. Each entry of a matrix again corresponds to a pixel in the image of the target area, such that an entry in the matrix is nonzero only if the beam passes through the corresponding pixel. Note that each beam matrix corresponds to a beam origin-angle combination; it is possible for there to be multiple beams in the set of possible beamlets with the same origin but aimed at different angles.

## Task 1
* Formulate a mathematical model.
* Even with lots of experience, an oncologist has a tendency to set the limits so that there are no feasible solutions. formulate a model that allows for a slight variation on the limits where it is necessary to ensure feasibility.
* formulate a variation of your model from the previous subtask that slightly penalizes radiation delivery to parts of the non-critical area that border a critical area.

## Task 2
* Implement the model. In this case, the model was implemented on Python using the Math and SciPy library.
* Test a sample scan (the binary matrix), with a relative intensity radiation beam matrix, under radiation constraints.
* Obtain the optimized dosage delivery matrix (the solution), and display the finding.
