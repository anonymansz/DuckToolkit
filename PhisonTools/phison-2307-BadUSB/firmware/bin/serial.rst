                                      1 ;--------------------------------------------------------
                                      2 ; File Created by SDCC : free open source ANSI-C Compiler
                                      3 ; Version 3.7.1 #10443 (MINGW64)
                                      4 ;--------------------------------------------------------
                                      5 	.module serial
                                      6 	.optsdcc -mmcs51 --model-small
                                      7 	
                                      8 ;--------------------------------------------------------
                                      9 ; Public variables in this module
                                     10 ;--------------------------------------------------------
                                     11 	.globl _com0isr
                                     12 	.globl _RI
                                     13 	.globl _TI
                                     14 	.globl _RB8
                                     15 	.globl _TB8
                                     16 	.globl _REN
                                     17 	.globl _SM2
                                     18 	.globl _SM1
                                     19 	.globl _SM0
                                     20 	.globl _RXD
                                     21 	.globl _TXD
                                     22 	.globl _INT0
                                     23 	.globl _INT1
                                     24 	.globl _T0
                                     25 	.globl _T1
                                     26 	.globl _WR
                                     27 	.globl _RD
                                     28 	.globl _PX0
                                     29 	.globl _PT0
                                     30 	.globl _PX1
                                     31 	.globl _PT1
                                     32 	.globl _PS
                                     33 	.globl _EX0
                                     34 	.globl _ET0
                                     35 	.globl _EX1
                                     36 	.globl _ET1
                                     37 	.globl _ES
                                     38 	.globl _EA
                                     39 	.globl _IT0
                                     40 	.globl _IE0
                                     41 	.globl _IT1
                                     42 	.globl _IE1
                                     43 	.globl _TR0
                                     44 	.globl _TF0
                                     45 	.globl _TR1
                                     46 	.globl _TF1
                                     47 	.globl _P
                                     48 	.globl _OV
                                     49 	.globl _RS0
                                     50 	.globl _RS1
                                     51 	.globl _F0
                                     52 	.globl _AC
                                     53 	.globl _CY
                                     54 	.globl _SBUF
                                     55 	.globl _SCON
                                     56 	.globl _IP
                                     57 	.globl _IE
                                     58 	.globl _TH1
                                     59 	.globl _TH0
                                     60 	.globl _TL1
                                     61 	.globl _TL0
                                     62 	.globl _TMOD
                                     63 	.globl _TCON
                                     64 	.globl _PCON
                                     65 	.globl _DPH
                                     66 	.globl _DPL
                                     67 	.globl _SP
                                     68 	.globl _B
                                     69 	.globl _ACC
                                     70 	.globl _PSW
                                     71 	.globl _P3
                                     72 	.globl _P2
                                     73 	.globl _P1
                                     74 	.globl _P0
                                     75 	.globl _PRAMCTL
                                     76 	.globl _BANK2PAH
                                     77 	.globl _BANK2PAL
                                     78 	.globl _BANK2VA
                                     79 	.globl _BANK1PAH
                                     80 	.globl _BANK1PAL
                                     81 	.globl _BANK1VA
                                     82 	.globl _BANK0PAH
                                     83 	.globl _BANK0PAL
                                     84 	.globl _WARMSTATUS
                                     85 	.globl _GPIO0OUT
                                     86 	.globl _GPIO0DIR
                                     87 	.globl _DMACMD
                                     88 	.globl _DMAFILL3
                                     89 	.globl _DMAFILL2
                                     90 	.globl _DMAFILL1
                                     91 	.globl _DMAFILL0
                                     92 	.globl _DMASIZEH
                                     93 	.globl _DMASIZEM
                                     94 	.globl _DMASIZEL
                                     95 	.globl _DMADSTH
                                     96 	.globl _DMADSTM
                                     97 	.globl _DMADSTL
                                     98 	.globl _DMASRCH
                                     99 	.globl _DMASRCM
                                    100 	.globl _DMASRCL
                                    101 	.globl _NANDCSDIR
                                    102 	.globl _NANDCSOUT
                                    103 	.globl _EP4
                                    104 	.globl _EP3
                                    105 	.globl _EP2
                                    106 	.globl _EP1
                                    107 	.globl _EP0
                                    108 	.globl _SETUPDAT
                                    109 	.globl _EP0CS
                                    110 	.globl _EPIE
                                    111 	.globl _EPIRQ
                                    112 	.globl _USBIRQ
                                    113 	.globl _USBSTAT
                                    114 	.globl _USBCTL
                                    115 	.globl _REGBANK
                                    116 ;--------------------------------------------------------
                                    117 ; special function registers
                                    118 ;--------------------------------------------------------
                                    119 	.area RSEG    (ABS,DATA)
      000000                        120 	.org 0x0000
                           000080   121 _P0	=	0x0080
                           000090   122 _P1	=	0x0090
                           0000A0   123 _P2	=	0x00a0
                           0000B0   124 _P3	=	0x00b0
                           0000D0   125 _PSW	=	0x00d0
                           0000E0   126 _ACC	=	0x00e0
                           0000F0   127 _B	=	0x00f0
                           000081   128 _SP	=	0x0081
                           000082   129 _DPL	=	0x0082
                           000083   130 _DPH	=	0x0083
                           000087   131 _PCON	=	0x0087
                           000088   132 _TCON	=	0x0088
                           000089   133 _TMOD	=	0x0089
                           00008A   134 _TL0	=	0x008a
                           00008B   135 _TL1	=	0x008b
                           00008C   136 _TH0	=	0x008c
                           00008D   137 _TH1	=	0x008d
                           0000A8   138 _IE	=	0x00a8
                           0000B8   139 _IP	=	0x00b8
                           000098   140 _SCON	=	0x0098
                           000099   141 _SBUF	=	0x0099
                                    142 ;--------------------------------------------------------
                                    143 ; special function bits
                                    144 ;--------------------------------------------------------
                                    145 	.area RSEG    (ABS,DATA)
      000000                        146 	.org 0x0000
                           0000D7   147 _CY	=	0x00d7
                           0000D6   148 _AC	=	0x00d6
                           0000D5   149 _F0	=	0x00d5
                           0000D4   150 _RS1	=	0x00d4
                           0000D3   151 _RS0	=	0x00d3
                           0000D2   152 _OV	=	0x00d2
                           0000D0   153 _P	=	0x00d0
                           00008F   154 _TF1	=	0x008f
                           00008E   155 _TR1	=	0x008e
                           00008D   156 _TF0	=	0x008d
                           00008C   157 _TR0	=	0x008c
                           00008B   158 _IE1	=	0x008b
                           00008A   159 _IT1	=	0x008a
                           000089   160 _IE0	=	0x0089
                           000088   161 _IT0	=	0x0088
                           0000AF   162 _EA	=	0x00af
                           0000AC   163 _ES	=	0x00ac
                           0000AB   164 _ET1	=	0x00ab
                           0000AA   165 _EX1	=	0x00aa
                           0000A9   166 _ET0	=	0x00a9
                           0000A8   167 _EX0	=	0x00a8
                           0000BC   168 _PS	=	0x00bc
                           0000BB   169 _PT1	=	0x00bb
                           0000BA   170 _PX1	=	0x00ba
                           0000B9   171 _PT0	=	0x00b9
                           0000B8   172 _PX0	=	0x00b8
                           0000B7   173 _RD	=	0x00b7
                           0000B6   174 _WR	=	0x00b6
                           0000B5   175 _T1	=	0x00b5
                           0000B4   176 _T0	=	0x00b4
                           0000B3   177 _INT1	=	0x00b3
                           0000B2   178 _INT0	=	0x00b2
                           0000B1   179 _TXD	=	0x00b1
                           0000B0   180 _RXD	=	0x00b0
                           00009F   181 _SM0	=	0x009f
                           00009E   182 _SM1	=	0x009e
                           00009D   183 _SM2	=	0x009d
                           00009C   184 _REN	=	0x009c
                           00009B   185 _TB8	=	0x009b
                           00009A   186 _RB8	=	0x009a
                           000099   187 _TI	=	0x0099
                           000098   188 _RI	=	0x0098
                                    189 ;--------------------------------------------------------
                                    190 ; overlayable register banks
                                    191 ;--------------------------------------------------------
                                    192 	.area REG_BANK_0	(REL,OVR,DATA)
      000000                        193 	.ds 8
                                    194 ;--------------------------------------------------------
                                    195 ; internal ram data
                                    196 ;--------------------------------------------------------
                                    197 	.area DSEG    (DATA)
                                    198 ;--------------------------------------------------------
                                    199 ; overlayable items in internal ram 
                                    200 ;--------------------------------------------------------
                                    201 ;--------------------------------------------------------
                                    202 ; indirectly addressable internal ram data
                                    203 ;--------------------------------------------------------
                                    204 	.area ISEG    (DATA)
                                    205 ;--------------------------------------------------------
                                    206 ; absolute internal ram data
                                    207 ;--------------------------------------------------------
                                    208 	.area IABS    (ABS,DATA)
                                    209 	.area IABS    (ABS,DATA)
                                    210 ;--------------------------------------------------------
                                    211 ; bit data
                                    212 ;--------------------------------------------------------
                                    213 	.area BSEG    (BIT)
                                    214 ;--------------------------------------------------------
                                    215 ; paged external ram data
                                    216 ;--------------------------------------------------------
                                    217 	.area PSEG    (PAG,XDATA)
                                    218 ;--------------------------------------------------------
                                    219 ; external ram data
                                    220 ;--------------------------------------------------------
                                    221 	.area XSEG    (XDATA)
                           00F000   222 _REGBANK	=	0xf000
                           00F008   223 _USBCTL	=	0xf008
                           00F009   224 _USBSTAT	=	0xf009
                           00F027   225 _USBIRQ	=	0xf027
                           00F020   226 _EPIRQ	=	0xf020
                           00F030   227 _EPIE	=	0xf030
                           00F048   228 _EP0CS	=	0xf048
                           00F0B8   229 _SETUPDAT	=	0xf0b8
                           00F1C0   230 _EP0	=	0xf1c0
                           00F200   231 _EP1	=	0xf200
                           00F240   232 _EP2	=	0xf240
                           00F280   233 _EP3	=	0xf280
                           00F2C0   234 _EP4	=	0xf2c0
                           00F608   235 _NANDCSOUT	=	0xf608
                           00F618   236 _NANDCSDIR	=	0xf618
                           00F900   237 _DMASRCL	=	0xf900
                           00F901   238 _DMASRCM	=	0xf901
                           00F902   239 _DMASRCH	=	0xf902
                           00F904   240 _DMADSTL	=	0xf904
                           00F905   241 _DMADSTM	=	0xf905
                           00F906   242 _DMADSTH	=	0xf906
                           00F908   243 _DMASIZEL	=	0xf908
                           00F909   244 _DMASIZEM	=	0xf909
                           00F90A   245 _DMASIZEH	=	0xf90a
                           00F90C   246 _DMAFILL0	=	0xf90c
                           00F90D   247 _DMAFILL1	=	0xf90d
                           00F90E   248 _DMAFILL2	=	0xf90e
                           00F90F   249 _DMAFILL3	=	0xf90f
                           00F930   250 _DMACMD	=	0xf930
                           00FA14   251 _GPIO0DIR	=	0xfa14
                           00FA15   252 _GPIO0OUT	=	0xfa15
                           00FA38   253 _WARMSTATUS	=	0xfa38
                           00FA40   254 _BANK0PAL	=	0xfa40
                           00FA41   255 _BANK0PAH	=	0xfa41
                           00FA42   256 _BANK1VA	=	0xfa42
                           00FA43   257 _BANK1PAL	=	0xfa43
                           00FA44   258 _BANK1PAH	=	0xfa44
                           00FA45   259 _BANK2VA	=	0xfa45
                           00FA46   260 _BANK2PAL	=	0xfa46
                           00FA47   261 _BANK2PAH	=	0xfa47
                           00FA48   262 _PRAMCTL	=	0xfa48
                                    263 ;--------------------------------------------------------
                                    264 ; absolute external ram data
                                    265 ;--------------------------------------------------------
                                    266 	.area XABS    (ABS,XDATA)
                                    267 ;--------------------------------------------------------
                                    268 ; external initialized ram data
                                    269 ;--------------------------------------------------------
                                    270 	.area XISEG   (XDATA)
                                    271 	.area HOME    (CODE)
                                    272 	.area GSINIT0 (CODE)
                                    273 	.area GSINIT1 (CODE)
                                    274 	.area GSINIT2 (CODE)
                                    275 	.area GSINIT3 (CODE)
                                    276 	.area GSINIT4 (CODE)
                                    277 	.area GSINIT5 (CODE)
                                    278 	.area GSINIT  (CODE)
                                    279 	.area GSFINAL (CODE)
                                    280 	.area CSEG    (CODE)
                                    281 ;--------------------------------------------------------
                                    282 ; global & static initialisations
                                    283 ;--------------------------------------------------------
                                    284 	.area HOME    (CODE)
                                    285 	.area GSINIT  (CODE)
                                    286 	.area GSFINAL (CODE)
                                    287 	.area GSINIT  (CODE)
                                    288 ;--------------------------------------------------------
                                    289 ; Home
                                    290 ;--------------------------------------------------------
                                    291 	.area HOME    (CODE)
                                    292 	.area HOME    (CODE)
                                    293 ;--------------------------------------------------------
                                    294 ; code
                                    295 ;--------------------------------------------------------
                                    296 	.area CSEG    (CODE)
                                    297 ;------------------------------------------------------------
                                    298 ;Allocation info for local variables in function 'com0isr'
                                    299 ;------------------------------------------------------------
                                    300 ;	serial.c:3: void com0isr(void) __interrupt COM0_VECT
                                    301 ;	-----------------------------------------
                                    302 ;	 function com0isr
                                    303 ;	-----------------------------------------
      0010F0                        304 _com0isr:
                           000007   305 	ar7 = 0x07
                           000006   306 	ar6 = 0x06
                           000005   307 	ar5 = 0x05
                           000004   308 	ar4 = 0x04
                           000003   309 	ar3 = 0x03
                           000002   310 	ar2 = 0x02
                           000001   311 	ar1 = 0x01
                           000000   312 	ar0 = 0x00
                                    313 ;	serial.c:5: }
      0010F0 32               [24]  314 	reti
                                    315 ;	eliminated unneeded mov psw,# (no regs used in bank)
                                    316 ;	eliminated unneeded push/pop psw
                                    317 ;	eliminated unneeded push/pop dpl
                                    318 ;	eliminated unneeded push/pop dph
                                    319 ;	eliminated unneeded push/pop b
                                    320 ;	eliminated unneeded push/pop acc
                                    321 	.area CSEG    (CODE)
                                    322 	.area CONST   (CODE)
                                    323 	.area XINIT   (CODE)
                                    324 	.area CABS    (ABS,CODE)
