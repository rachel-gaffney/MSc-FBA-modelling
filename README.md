# MSc-FBA-modelling
Aim: Formulate a systematic method to construct multilinear objective functions to model qualitative CHO experimental flux data during the late exponential phase.

• `iCHO2441_221-107_producing.xml` is an adapted iCHO2441 GEM (<a href="https://pubmed.ncbi.nlm.nih.gov/36866411/">Strain et al. 2023</a>) with  reactions relating to mAb production updated to represent the product profile of the Apollo X CHO-DG44 cell line (FUJIFILM Diosynth Biotechnologies).

• `bounds_df.csv` contains transcriptomics data-derived bounds for the late exponential time point, obtained from <a href="https://analyticalsciencejournals.onlinelibrary.wiley.com/doi/10.1002/bit.28982">Meeson et al. 2025</a>.

• `linear_FBA_objectives.ipynb` systematically tests FBA solutions for the adapted iCHO2441 model using objective functions consisting of individual bioproduction reactions (biomass and IgG production, glucose and glutamine uptake, lactate and ammonia secretion) for alignment with qualitative criteria for these reactions, experimentally derived in <a href="https://analyticalsciencejournals.onlinelibrary.wiley.com/doi/10.1002/bit.28982">Meeson et al. 2025</a>.

• `enumerating_feasible_FVA_objectives.ipynb` systematically evaluates Loopless FVA solutions for the adapted iCHO2441 model using objective functions constructed from all 3 reaction combinations of the bioprocess reactions, incrementing in weighting by steps of 0.1, and outputs those objective combinations where the optimal flux range includes the qualitative success criteria.

• `testing_feasible_loopless_FVA_solutions.ipynb` tests the combinations identified as feasible from Loopless FVA using Loopless FBA on the adapted iCHO2441 model to confirm if any successfully model qualitative criteria.

• `sampling_loopless_pFBA_solutions.ipynb` samples all n-linear reaction combinations, starting with n=1 and incrementing with a sensitivity/step length of 0.01, and optimises the iCHO2441 GEM to maximise loopless, pFBA flux through each of these objective functions. All combinations which successfully model the qualitative criteria are outputted, as the minimal parsimonious and loopless objective functions to qualitatively model this data with the given sensitivity. If no solutions are found, then n=n+1 and the method is repeated.

• `fit_objective_function.ipynb` uses simulated annealing to identify an optimal objective function combination for a given set of reactions, which minimises qualitative mismatch from standard FBA, pFBA or loopless FBA solutions and qualitative flux criteria. This script also includes a faster version of the standard FBA method which approximates halves runtime.


The project scope was then extended to model early exponential and stationary/death phase qualitative flux data:

• `early_exponential_bounds.csv` contains transcriptomics data-derived bounds for the early exponential time point, obtained from <a href="https://analyticalsciencejournals.onlinelibrary.wiley.com/doi/10.1002/bit.28982">Meeson et al. 2025</a>.

• `stationary_death_bounds.csv` contains transcriptomics data-derived bounds for the stationary/death time point, obtained from <a href="https://analyticalsciencejournals.onlinelibrary.wiley.com/doi/10.1002/bit.28982">Meeson et al. 2025</a>.

• `Early_Exponential_objective_fitting.ipynb` uses the simulated annealing-based methodology to identify an optimal objective function combination for early exponential qualitative flux criteria, experimentally derived in <a href="https://analyticalsciencejournals.onlinelibrary.wiley.com/doi/10.1002/bit.28982">Meeson et al. 2025</a>.

• `Stationary_Death_objective_fitting.ipynb` uses the simulated annealing-based methodology to identify an optimal objective function combination for stationary/death phase qualitative flux criteria, experimentally derived in <a href="https://analyticalsciencejournals.onlinelibrary.wiley.com/doi/10.1002/bit.28982">Meeson et al. 2025</a>.
