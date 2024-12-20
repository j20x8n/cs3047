java c
System and Networks 
COMPSCI 4043 
Monday 26 April 2021 
1.          (a)             Express the following   in   32-bit two’s   complement   code,   giving   your   answers   in   hexadecimal.   Show   your   working.
i.                      1023                               ii.                     -1023 [4] 
(b)          If the   calculation   100   +   30   –   20   is   performed   by   an   8-bit   CPU,   using   an   8-bit two’s   complement
code, will an overflow   be generated?   Explain your answer and   say   what   result you’d   expect   to   be   generated. [3] 
(c)             For the   mathematical set of   integers, subtraction   is   always   the   same   as   adding   the   inverse   of   a      number. Thus 3 – 2   = 3 +   (-2)   and   3 –   (-2)   =   3 +   2.   Is this   also   true   for   a   two’s   complement   code?   Justify your answer. [2] 
(d)          Write a Sigma16   program   that   accesses   an   array   X   of n 16-bit two’s   complement   numbers   and   for
each element X[i]   in X, stores a 0   or   1   in the   corresponding   element of   a   second   array   Y   according   to   the following   rule.
Y[i] = 0   if X[i]   is   odd; Y[i]   =   1   if Y[i]   is   even [7] 
(e)          Write a   segment   of   Sigma16   code   (not   a   complete   program)   which   sets   R2 to   0   if the second most significant bit in   R1 is a 0,   and   sets   R2 to   1,      otherwise.   Estimate   how   many   Sigma16   cycles your segment will take to   run as you’ve written   it. [4] 
For   reference,   here   is   part of the   instruction set of the   Sigma16 CPU.
lea 
Rd, x[Ra] 
Rd:= x +Ra 
load 
Rd, x[Ra] 
Rd:= mem[x +Ra] 
store 
Rd, x[Ra] 
mem[x +Ra]:=Rd 
add 
Rd,Ra,Rb 
Rd:= Ra+Rb 
sub 
Rd,Ra,Rb 
Rd:= Ra-Rb 
mul 
Rd,Ra,Rb 
Rd:= Ra*Rb 
div 
Rd,Ra,Rb 
Rd:= Ra/Rb,    R15:=Ra mod Rb 
and 
Rd,Ra,Rb 
Rd:= Ra AND Rb 
inv 
Rd,Ra,Rb 
Rd:= NOT Ra 
or 
Rd,Ra,Rb 
Rd:= Ra OR Rb 
xor 
Rd,Ra,Rb 
Rd:= Ra XOR Rb 
cmplt 
Rd,Ra,Rb 
Rd:= Ra  
cmpeq 
Rd,Ra,Rb 
Rd:= Ra=Rb 
cmpgt 
Rd,Ra,Rb 
Rd:= Ra>Rb 
shiftl 
Rd,Ra,Rb 
Rd:=Ra logic shifted left Rb places 
shiftr 
Rd,Ra,Rb 
Rd:=Ra logic shifted right Rb places 
jumpf 
Rd, x[Ra] 
If Rd=0 then PC:=x+Ra 
jumpt 
Rd, x[Ra] 
If Rd<>0 then PC:=x+Ra 
jal 
Rd, x[Ra] 
Rd:= pc, pc: =x +Ra 
trap 
Rd,Ra,Rb 
PC:= interrupt handler 
jump 
x[Ra] 
PC:= x +Ra 
2                (a)                How do cache   memories speedup   program execution?   Many   caches   only   cache   read   cycles.   Why   is   this
and why   is   it   usually   not seen as a   major   limitation?   Discuss wheth代 写COMPSCI 4043 System and Networks 2021R
代做程序编程语言er there are   circumstances   where   caching write cycles would   provide some   benefit. [6] 
(b)             The following Sigma   16 code   is   intended to take a   10-element array   of two’scomplement   numbers   (only   first element is shown) and   replace all the   elements   with   their   twos   complement   inverse.   The   number $8000 is   not   permitted.   However, although the code will assemble,   it   contains   several   errors.
i.                   Draw   up aregister   use   table for   the   program   (suitable   for   inclusion   as   comment).
ii.                   Identify the errors   and   explain   how you   would   correct   them.
iii.                   Write   out the   corrected   program.

LOAD 
R1,1[R0] ;Set R1 to constant 1 

ADD 
R2,R0,R0 
;i:=0 

LOAD 
R3,n[R0] 
;Set R3 ton 
FORLOOP 
CMPEQ R5,R2,R3 
;Is i  

JUMPF 
R5,OUT[R0] 
;if yes, exit 

LOAD 
R4,X[R2] 
;load x[i] 

INV 
R4,R4,R0 
;R6= -x[i] 

ADD 
R1,R2,R2 
;i:=i+1 

STORE 
R4,X[R2] 
;x[i]=-x[i] 

JUMP 
FORLOOP[R0] 
;loop
OUT                                                             TRAP R0,R0,R0 
; Data Area 
href="#bookmark2" X                                                                                  DATA            -8 [6] 
(c)                Estimate   how   many   memory cycles the corrected   program would take to   run. [4] 
(d)             In the corrected   program estimate the   advantage   a   system   with   a   cache   memory   would   gain   if   a   primary   memory cycle takes   10ns and a   cache   cycle   1ns. [4]
3.                            (a)                               In   Internet communications,   how does   a   router   get   an   IP   packet to   its   destination?   Explain   why   the   routing approach   used   by   IP would   not work with either a TCP   segment   or   an   Ethernet   frame. [6] 
(b)                            An   IP   interface   has the address 192.10.0.1.   What   binary value   does this   address   represent?   Also   write the value   in   hex. [3] 
(c)                               “   IP   is   not   reliable and   IP carries TCP; therefore, TCP cannot   be   reliable either.”      Comment   on the         truth of the   premises and conclusion of this argument   and   discuss   whether   the   reasoning   is   valid. [6] 
(d)                            Many TCP   connections   can   be   running   simultaneously   on   a   given   host   machine.   Referring   to   what   you   know about the communication system and   its   relationship to the   operating   system,   explain         how this   is   possible. [5] 

         
加QQ：99515681  WX：codinghelp  Email: 99515681@qq.com
