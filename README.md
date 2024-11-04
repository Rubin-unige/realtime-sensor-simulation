# Real-Time Sensor Simulation

This project simulates real-time sensor data generation and processing using POSIX threads. It aims to demonstrate how to handle multiple sensor inputs concurrently and aggregate data in a structured manner, mimicking basic principles found in embedded systems.

## Project Timeline Breakdown

### Initial Setup and Planning (1-2 hours)

- **Define Project Scope**: 
  - Decide which "sensors" you’ll simulate (e.g., temperature, pressure, light).
  - Define the structure of the data (e.g., integer or float values).

- **Set Up Development Environment**: 
  - Ensure you have a compiler (like `gcc`), necessary libraries, and an editor (like VS Code or Vim).

- **Design Structure**: 
  - Plan out the program structure, including the use of threads for each sensor and a main thread for processing.

### Implement Sensor Simulation Threads (2-3 hours)

- **Create Threads**: 
  - Use `pthread_create` to launch threads for each sensor.

- **Simulate Sensor Data**: 
  - Write code within each thread to generate random or incremental values that mimic real sensor data, updating every second or so.

- **Timing and Synchronization**: 
  - Use POSIX timers (`nanosleep`, `clock_gettime`) to control how often each sensor updates.

- **Output Simulation**: 
  - Print generated sensor values to the console to confirm everything is working as expected.

### Implement Data Processing and Aggregation (2 hours)

- **Shared Memory**: 
  - Use shared memory (e.g., a struct or array) to store sensor data. Use `pthread_mutex_t` to lock data access for safe reads/writes.

- **Data Aggregation Thread**: 
  - Implement a separate processing thread that periodically reads from shared memory, performs an aggregation (e.g., averaging), and logs results.

- **Thread Synchronization**: 
  - Use mutexes and condition variables to synchronize sensor updates with the processing thread.

### Testing and Debugging (1-2 hours)

- **Test Timing and Synchronization**: 
  - Ensure each sensor updates data independently and confirm the processing thread is reading data in real-time without issues.

- **Edge Cases**: 
  - Test for cases where sensor threads might be updating data while the processing thread is reading.

- **Debugging Tools**: 
  - Use `gdb` or print statements to troubleshoot any synchronization or timing issues.

### Optional Enhancements (2-3 hours)

- **Logging to File**: 
  - Add functionality to log aggregated data to a file for persistent storage.

- **Signal Handling**: 
  - Add graceful termination (using signals like `SIGINT`) to ensure all threads close properly.

- **Real-Time Scheduling**: 
  - If you're comfortable, experiment with POSIX real-time scheduling policies (like `SCHED_RR`) to prioritize processing.

## Getting Started

To get started, clone the repository and open it in your preferred development environment. Ensure you have the required dependencies installed.

```bash
git clone https://github.com/yourusername/realtime-sensor-simulation.git
cd realtime-sensor-simulation
