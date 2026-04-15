# DFT-Bench

A benchmark dataset for evaluating AI models on DFT (Density Functional Theory) calculations.

## Purpose

DFT-Bench provides standardized datasets of DFT calculations to benchmark and compare AI models that predict material properties. The goal is to create a comprehensive test suite that measures how well AI models can reproduce DFT results without performing the actual expensive calculations.

## Workflow

1. **Select Dataset**: Choose from Material Cloud or Materials Project
2. **Download**: Fetch the raw DFT calculation data
3. **Parse**: Extract three components:
   - **Structure**: Atomic positions, cell parameters, crystal structure
   - **Situation Details**: Calculation parameters (k-points, functionals, cutoffs)
   - **Results**: Band structures, DOS, total energies, forces, etc.
4. **Benchmark**: Use parsed data to test AI models
5. **Compare**: Evaluate which AI models best reproduce DFT results

## Data Sources Under Consideration

### Materials Project (MP)
- **Pros**: Large dataset (~150k materials), well-documented API, standardized calculations
- **Cons**: May have different convergence criteria across historical calculations

### Material Cloud (MC)
- **Pros**: High-quality curated datasets, reproducibility focus, recent calculations
- **Cons**: Smaller dataset, less coverage

## Initial Decision

**Starting with Material Cloud** due to:
- Higher reproducibility standards
- Better documented calculation parameters
- Cleaner data structure for parsing
- Focus on well-converged results

Materials Project can be integrated later for larger-scale validation.

## Repository Structure

```
dft-bench/
├── data/               # Downloaded and parsed datasets
├── parsers/            # Scripts to parse raw DFT outputs
├── benchmarks/         # Benchmarking scripts
├── models/             # AI model interfaces
└── results/            # Benchmark results
```

## Next Steps

1. Select initial Material Cloud dataset
2. Implement parser for structure extraction
3. Implement parser for calculation parameters
4. Implement parser for results (bands, DOS, etc.)
5. Create AI model interface
6. Run initial benchmarks

## License

MIT License
