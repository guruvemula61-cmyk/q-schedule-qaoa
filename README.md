# Q-Schedule: QAOA-Based Exam Timetable Clash Optimizer

Proof-of-concept that formulates exam timetabling as Max-Cut, solves it
with QAOA using IBM Qiskit, and benchmarks it against greedy and
brute-force methods. We do not claim quantum advantage at this scale.

## Problem
Subjects are nodes; edge weight = number of students enrolled in both.
For two slots, minimising clashes = maximising the weighted cut.

## Pipeline
Enrollment CSV -> clash graph -> QUBO/Ising -> QAOA (p=1,2,3, COBYLA)
-> Aer simulation -> IBM Quantum hardware (Qiskit Runtime Sampler)
-> timetable + benchmark charts

## Results
(to be filled after running the notebook)

## Run it
pip install -r requirements.txt
jupyter notebook Q_Schedule_QAOA.ipynb
streamlit run app.py

For hardware runs, save your IBM Quantum API token using
QiskitRuntimeService.save_account(...). Never commit your token.

## Notes
- Max-Cut is symmetric: a bitstring and its complement give the same cut,
  so histograms show two peaks.
- Qiskit bitstrings are little-endian; decoding reverses the order.
- Data is synthetic. Room and invigilator constraints are future work.

## Tools
Python, Qiskit, Qiskit Aer, Qiskit Runtime, qiskit-algorithms,
qiskit-optimization, NetworkX, NumPy, Pandas, Streamlit, Plotly

## Team
(add team member names)
