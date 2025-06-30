# OS-Page-Replacement-and-Scheduling-Algorithms

* Developed a simulation framework that generates synthetic page‑reference streams based on RAM capacity and process count.
* Evaluated OPT, FIFO, LRU, and MRU page‑replacement algorithms across all feasible page‑sizes, reporting comprehensive hit‑rate comparisons.
* Employed object‑oriented design to create modular, extensible, and loosely coupled classes, adhering to industry‑level coding standards.
* Incorporated system‑design patterns—such as the Singleton—to streamline architecture and ensure efficient state management.


## Flow of the Project

main()
 └─► handler::createHandler()
     ├─ input::getInput() → user enters (noOfProcess, RAMSize, processSize)
     ├─ output::getOutput()
     └─ history::updateHistory(input, output)

 └─► handler::analyzeOnAllPageSize()
     └─ for each pageSize = 0…min(RAMSize,processSize):
         ├─ analyze = createAnalyze(...)
         └─ analyze->runProcesses():
             └─ for each process (0…noOfProcess–1):
                 ├─ proc = createProcess(...)
                 ├─ results = proc->runProcess():
                 │    └─ for each algorithm in {OPT, FIFO, LRU, MRU}:
                 │         instantiate RAM subclass → processRAM() → {miss,total}
                 └─ mergeOutput(results)
         └─ output->mergeOutput(analyze.curOutput)

 └─► handler::printAnalyzedData()
     └─ history::printCurrentStats() → build & print hit‑rate table





