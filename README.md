<h1 align="center">FPGA Stopwatch</h1>


<p align="center">
    <img src="https://user-images.githubusercontent.com/110432500/233398339-0f5bbb6b-e43a-4e2b-a883-d7914d275d62.gif" alt="Quick demonstration of the stopwatch" width=300 />
<p align="center">

This project creates a standard stopwatch using an FPGA — more specifically, the <a href="https://www.terasic.com.tw/cgi-bin/page/archive.pl?Language=English&No=921">DE0-CV FPGA Board</a>. When the user flips a specific switch, the stopwatch begins to visibly count up in minutes and seconds; this is represented on the board's seven-segment display using decimal (base ten) numbers.
    
If the switch is flipped back to its original position by the user, the stopwatch pauses and the display freezes. The stopwatch will not resume counting until the switch is activated yet again.

## Circuit design




<p align="center">
    <img src="https://user-images.githubusercontent.com/110432500/233406811-15d94ed3-a714-420e-a262-2dae64a06bee.PNG" alt="Circuit #1 - counts by seconds" />
    <b>Figure 1</b>
</p>

<p align="center">
    <img src="https://user-images.githubusercontent.com/110432500/233406806-c0eca815-263a-413c-a851-1d03b6a15854.PNG" alt="Circuit #2 - counts by minutes" />
    <b>Figure 2</b>
</p>
    

    
    
