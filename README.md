# opencl-cpu-vs-gpu-tutorial-for-windows-10
comapring a matrix multiplication on CPU vs GPU on Windows 10 using OpenCL



Setup OpenCL on our system and run Matrix Multiplication code on CPU and GPU to compare the two of them. Remember that the performance may vary significantly from system to system and different hardware specs. Therefore, it is important to notice the details of hardware we are using. Following snapshot shows the DXDIAG results on my Core i3, Windows laptop PC.

The code I have chosen is sourced from a freely published gist on GitHub by Tanay Prabhu Desai [https://gist.github.com/tanayseven/726c50a1dc419ea57e64]. This code contains a matrix multiplication code for a pre-filled matrix of size 3x3. Navigate to the folder containing codes, and compile with this command in CMD:
gcc -I. mat_mul.c C:\Windows\System32\OpenCL.dll -o main.exe
 
## Note the time using PowerShell with this:
Measure-Command {start-process mat_mul.exe -wait}
To run on CPU, go to line 157, change CL_DEVICE_TYPE_*** to CL_DEVICE_TYPE_CPU, recompile and re-run. Now change the device type to GPU and recompile.
To run on GPU, go to line 157, change CL_DEVICE_TYPE_*** to CL_DEVICE_TYPE_GPU, recompile and re-run. Notice the time taken by two in following figure.
 
As you can see that there is a clear difference between the running time of two. Running time of CPU is 4x as compared to GPU.
	•	Time taken by CPU is 12334.7391 ms
	•	Time taken by GPU is 2288.8545 ms

