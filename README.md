<h1 align="center">FPGA Stopwatch</h1>

<p align="center">
  <a href="#about">About</a> &nbsp;&nbsp;•&nbsp;&nbsp; 
  <a href="#circuit-design">Circuit design</a> &nbsp;&nbsp;•&nbsp;&nbsp;
  <a href="#notes">Notes</a>
</p>

<p align="center">
    <img src="https://user-images.githubusercontent.com/110432500/233398339-0f5bbb6b-e43a-4e2b-a883-d7914d275d62.gif" alt="Quick demonstration of the stopwatch" width=300 />
<p align="center">

## About

In this project, a standard stopwatch was created using an FPGA — more specifically, the <a href="https://www.terasic.com.tw/cgi-bin/page/archive.pl?Language=English&No=921">DE0-CV FPGA Board</a>. When the user flips a specific switch, the stopwatch begins to count the number of minutes and seconds elapsed; these values are represented on the board's seven-segment display using decimal (base ten) numbers. Though this display choice is a more complex approach than the standard binary-coded decimal (BCD) display, it is much more understandable and easy to read for the common user.

    
If the switch is flipped back to its original position by the user, the stopwatch pauses and the display freezes accordingly, thus retaining the time that was on the stopwatch when it was paused. The stopwatch will remain paused until the user flips the switch back into the "on" setting, at which point the stopwatch will continue counting from where it left off.

In simpler terms: if you flip the switch on, the stopwatch starts. If you flip the switch off, the stopwatch pauses, and it will stay paused until you flip the switch back on. In order to reset the stopwatch back to 0 seconds, you have to hit the "Reset" button on the FPGA board.
    
## Circuit design

The stopwatch was implemented using two embellished counter circuits that were connected to become a larger circuit.

Using code from a previous lab project (**Figure 0**), Counter Circuit #1 (**Figure 1**) was set to have an interval of exactly one second between increments. This is the circuit that counts the seconds that elapse. This counter continuously checks if it has reached 60 seconds; if so, an incrementation signal is sent to Counter #2 (in order to tell Counter #2 to increment by one minute), and Counter #1 resets back to 0 seconds.

On the other hand, Counter Circuit #2 (**Figure 2**) was set to have an interval of exactly one minute between increments; as previously stated, this was achieved by setting Counter #1 to send an incrementation signal to Counter #2 every time Counter #1 reaches 60 seconds; this triggers Counter #2 to increment by 1. Thus, Counter #2 keeps track of how many minutes have elapsed.

&nbsp;

<p align="center">
    <img src="https://user-images.githubusercontent.com/110432500/233460138-96c9209b-ef92-4c6b-9a07-22d0725e26ad.png" alt="Code used to set counter increment interval to 1 second" />
    <br>
    <b>Figure 0: </b>
    Circuit #1 increment interval code
</p>

&nbsp;&nbsp;

<p align="center">
    <img src="https://user-images.githubusercontent.com/110432500/233462242-c0db16e2-c356-4672-a991-86119fe03759.png" alt="Counter circuit #1 — counts by seconds" />
    <b>Figure 1: </b>
    Counter circuit #1 – counts by seconds
</p>

&nbsp;&nbsp;

<p align="center">
    <img src="https://user-images.githubusercontent.com/110432500/233463285-a154354b-39f5-447e-8763-f567891063e5.png" alt="Counter circuit #2 — counts by minutes" />
    <b>Figure 2: </b>
    Counter circuit #2 – counts by minutes
</p>

## Notes
The circuit was designed using the FPGA design software [Intel Quartus Prime](https://www.intel.com/content/www/us/en/products/details/fpga/development-tools/quartus-prime.html). If you would like to view or alter the circuit schematics, feel free to import the ZIP file in this repository into Quartus.
