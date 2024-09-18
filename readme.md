# Data Engineer Technical Challenge

This technical challenge is designed for the Data Engineer role, with an emphasis on your ability to work efficiently with data pipelines, optimization, and containerization.

## Objective

- Process the provided data files in the `data` folder.
- Extract, transform, and load (ETL) the day files.
- Generate phase- and module-specific day files, ensuring a **5-second sampling rate**.
- Store the processed data in the `output` folder.
- Visualize the data using appropriate plots.

## Requirements

1. **Folder Structure**:
   - The data should be segregated and stored in the following folder structure:
   - {phase}_{module}/year/month/day/hour.parquet.
   - This parquet file shall only contain the data of the respective hour. (Eg: 15.parquet goes from 15:00 to 16:00, following the 24 hour format)

2. **Data structure**:
   - The data shall be structured in columns.<br>
For example, if the phase module has module_voltage, we shall have the module_voltage column in the output hour file.
   - Phase X Module Y shall only contain the respective data belonging to this module and phase. 
1. **Jupyter Notebook**:
   - The notebook should contain the entire workflow, from data ingestion to plotting.
   - It should demonstrate the ETL process and provide visualizations based on the various columns in the data.

2. **Python CLI Script**:
   - A standalone Python script that performs the ETL process and generates the required parquet files.
   - Ensure that it can be executed from the command line.

3. **Docker Container**:
   - Create a `Dockerfile` to containerize the Python script, ensuring that it can be executed in any environment.
   - The container should have all necessary dependencies (e.g., pandas, pyarrow, matplotlib, tqdm).

## Expected Deliverables

1. **Code Quality**:
   - Clean, modular, and self-explanatory code.
   - Code should follow best practices for readability and maintainability.
   
2. **Parquet Files**:
   - Include all columns present in the original data.
   - Ensure the files conform to a **5-second sampling rate**.

3. **Graphs**:
   - Plot data in relation to time, using columns present in the generated data files.
   - All visualizations should be well-labeled and clear.

4. **Containerized Solution**:
   - The solution should run within a Docker container, making it portable and reproducible.

5. **Optimized Processing**:
   - Ensure the ETL process is optimized for performance, considering both memory and time complexity.

## Tools & Libraries

- **pandas** with **pyarrow** for efficient DataFrame operations and parquet file generation.
- **matplotlib** for plotting and visualizing data.
- **tqdm** for progress tracking.
- **Docker** for containerization of the pipeline.


## Execution Steps

We expect to be able to execute your technical challenge using:

1. **Jupyter Notebook**:
   - Open the provided notebook and execute the code to see the ETL process and plotting process.

2. **Python CLI Script**:
   - We shall be able to execute the ETL script from the command line like so:
     ```bash
     python solution.py --input data/ --output output/
     ```

3. **Docker Container**:
   - We shall be able to build and run the Docker container:
     ```bash
     docker build -t data-engineer-challenge .
     docker run -v $(pwd)/data:/app/data -v $(pwd)/output:/app/output data-engineer-challenge
     ```


## Notes

- Ensure that the processed parquet files maintain the required 5-second sampling rate.
- All processing steps, from data cleaning to file generation, should be optimized for performance.
- After concluding this technical challenge, please provide access to jobs@circunomics.com
- This repo shall be kept private. Not keeping your technical challenge private will equal to disqualification.


