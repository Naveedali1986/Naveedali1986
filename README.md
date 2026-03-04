Numerical Modeling of Marine Vehicle Hydrodynamics
Overview
This repository presents numerical models of seakeeping, maneuvering, and resistance for marine vehicles. It uses Star-CCM+ (CFD), MATLAB (post-processing/control), and Python (automation/analysis). This work analyzes fluid-structure interactions and predicts vessel performance in varied marine environments.
The accurate prediction of marine vehicle behavior remains a fundamental challenge in naval architecture and ocean engineering. Traditional experimental methods, while valuable, are often expensive, time-consuming, and constrained by scale effects and facility limitations. This research addresses these challenges through comprehensive numerical modeling approaches that combine the fidelity of computational fluid dynamics with the flexibility of mathematical modeling and data-driven analysis.

Research Context and Motivation
Marine vehicles operating in real sea conditions encounter complex hydrodynamic phenomena that govern their performance, safety, and operational effectiveness. Understanding these phenomena requires a multi-faceted approach that captures:

Resistance characteristics: The forces opposing steady forward motion, including frictional resistance, wave-making resistance, and viscous pressure resistance, which directly determine powering requirements and fuel efficiency.
Seakeeping behavior: Vessel responses to waves, including motions in six degrees of freedom, wave-induced loads, and operability limitations that affect mission effectiveness and crew comfort.
Maneuvering capabilities: The ability to change direction, maintain course, and execute controlled movements, which is critical for navigation safety, station-keeping, and dynamic positioning.

Computational Methodology
Star-CCM+ for High-Fidelity CFD Simulations
The core of the hydrodynamic analysis relies on Siemens Star-CCM+, a comprehensive multiphysics simulation platform. Key applications include:

Resistance predictions: Steady-state simulations using the Volume of Fluid (VOF) method to capture the free surface around hulls. These simulations employ Reynolds-Averaged Navier-Stokes (RANS) equations with appropriate turbulence models (k-ε, k-ω SST, or Reynolds Stress models) depending on the flow characteristics. Mesh refinement studies ensure grid convergence, while validation against experimental data establishes confidence in prediction accuracy.
Seakeeping analysis: Dynamic fluid-body interaction (DFBI) simulations capture vessel motions in regular and irregular waves. Overset mesh techniques enable large-amplitude motions without mesh distortion, allowing accurate prediction of added resistance in waves, motion response amplitude operators (RAOs), and wave-induced loads.
Maneuvering simulations: Forced motion tests, including static drift, pure sway, and yaw oscillation maneuvers, are simulated to extract hydrodynamic coefficients for mathematical models. Planar Motion Mechanism (PMM) simulations provide systematic data for system identification.
Propeller-hull interaction: Combined simulations using sliding mesh or moving reference frame approaches capture the complex interaction between propulsion systems and the hull, including wake fraction, thrust deduction, and hull efficiency components.

MATLAB for Analysis and Control
MATLAB serves as the primary platform for data analysis, mathematical modeling, and control system development:

Post-processing and visualization: Custom scripts process large datasets from CFD simulations, extracting forces, moments, and motion histories. Statistical analysis identifies dominant frequencies and response characteristics.
System identification: CFD-generated force and moment data inform the development of reduced-order models. Maneuvering coefficients for Abkowitz, MMG, or other mathematical models are estimated through regression analysis and optimization techniques.
Control algorithm development: PID controllers, autopilot systems, and dynamic positioning algorithms are developed and tested using simplified vessel models before implementation in full-scale systems.
Motion prediction: Time-domain simulations using coupled differential equations predict vessel trajectories and motions under specified environmental conditions and control inputs.

Python for Automation and Data Science
Python complements the workflow through automation, data management, and advanced analytics:

Workflow automation: Scripts automate the setup of parametric studies, managing thousands of simulation cases efficiently. Batch processing capabilities enable systematic variation of geometric parameters, speeds, and wave conditions.
Data extraction and management: Custom parsers extract relevant quantities from simulation output files, organizing results into structured databases for further analysis.
Visualization and reporting: Matplotlib, Plotly, and PyVista generate publication-quality figures and interactive visualizations of flow fields, pressure distributions, and motion histories.
Machine learning applications: Surrogate models trained on CFD data enable rapid exploration of design spaces and real-time performance predictions during optimization studies.

Research Focus Areas
Resistance and Powering:
Systematic investigation of hull form parameters affecting calm water resistance. Studies include bulbous bow optimization, stern shape effects, and trim optimization for minimal resistance across operational speeds. Correlation allowances and scale effects are addressed through full-scale CFD predictions.
Seakeeping and Operability:
Comprehensive assessment of vessel motions in irregular seas using spectral analysis and short-term statistics. Motion sickness incidence (MSI), slamming probabilities, and deck wetness are evaluated to determine operational limits and guide design modifications.
Maneuvering and Course-Keeping:
Development of maneuvering prediction models based on CFD-generated hydrodynamic derivatives. Turning circles, zig-zag maneuvers, and course-keeping abilities are simulated and validated against free-running model tests where available.
Fluid-Structure Interaction:
Analysis of flexible structures and their interaction with surrounding fluids, including slamming loads on high-speed craft, hydroelastic effects in lightweight structures, and dynamic response of appendages and control surfaces.

Integrated Workflow
The true strength of this research lies in the integration of these tools into a cohesive workflow:
Geometry preparation and meshing in Star-CCM+ using Python-scripted parametric variations
CFD simulations executed in batches with automated monitoring and error handling
Data extraction using Python scripts that interface directly with simulation output
Analysis and modeling in MATLAB, including system identification and coefficient extraction
Validation and visualization combining MATLAB statistical tools with Python visualization libraries
Design feedback through automated reporting and interactive dashboards

Applications and Impact
The methodologies developed in this research support multiple objectives:
Design optimization: Identifying hull form modifications that reduce resistance, improve seakeeping, or enhance maneuverability
Performance prediction: Providing reliable estimates of vessel performance for operators and designers
Safety assessment: Evaluating vessel behavior in extreme conditions to establish safe operating envelopes
Regulatory compliance: Supporting compliance with stability, powering, and maneuvering requirements

Future Directions
Ongoing work explores high-performance computing for大规模 parametric studies, uncertainty quantification in CFD predictions, and the integration of machine learning for real-time performance monitoring and adaptive control systems.
