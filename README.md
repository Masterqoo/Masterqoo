// ตัวอย่างการสร้างวงจรควอนตัมด้วย Qiskit
from qiskit import QuantumCircuit, transpile, Aer, execute

def create_quantum_circuit():
    qc = QuantumCircuit(2)
    qc.h(0)
    qc.cx(0, 1)
    return qc

qc = create_quantum_circuit()
from qiskit import QuantumCircuit, Aer, transpile, execute

qc = create_quantum_circuit()
simulator = Aer.get_backend('qasm_simulator')
compiled_circuit = transpile(qc, simulator)
result = execute(compiled_circuit, simulator).result()
counts = result.get_counts()
print(counts)
