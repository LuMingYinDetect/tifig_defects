Affected Version:
tifig 0.2.2 60b920c06fdf1240936ef73668b03457ebb8e813

Vulnerability Description:
The vulnerability is a memory leak bug located at line 118 of the file /tifig/src/hevc_decode.hpp. This vulnerability could potentially be exploited maliciously to cause resource exhaustion and denial of service attacks.

tifig download address:
https://github.com/monostream/tifig.git

1.In /tifig/src/hevc_decode.hpp, a pointer variable named errorDescription is defined on line 87, and memory of size 256 is dynamically allocated to it using the new operator. When both the if condition statements on lines 90 and 98 evaluate to false, the function will return the result on line 118. During this period, the program neither utilizes the pointer variable nor deallocates the memory allocated to the variable's pointer. This results in a memory leak defect, as depicted below:

![image](https://github.com/LuMingYinDetect/tifig_defects/blob/main/tifig_1.png)
