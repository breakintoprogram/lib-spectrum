;
; Title:        Macros
; Author:       Dean Belfield
; Created:	06/02/2020
; Last updated: 05/04/2020
;
; Requires:	
;
; Modinfo:
;
; 05/04/2020:	Local labels now used in macros. Added MIN and MAX

MIN:			MACRO P1			; Get min of P1 and A in A
			CP P1				; Compare A with P1
			JR C, .S1			; Skip if P1 > A
			LD A, P1			; Assign P1 to A
.S1			;
			ENDM

MAX:			MACRO P1			; Get max of P1 and A in A
			CP P1				; Compare A with P1
			JR NC, .S1			; Skip if P1 > A
			LD A, P1			; Assign P1 to A
.S1			;
			ENDM

LD_BC_A:		MACRO 
			LD C, A 			; Turn A into 16 bit number 
			ADD A, A			; Push sign into carry
			SBC A, A 			; Turn into 0 or -1 (0xFF)
			LD B, A				; Store in MSB
			ENDM

LD_DE_A:		MACRO 
			LD E, A 
			ADD A, A
			SBC A, A 	
			LD D, A	
			ENDM

LD_HL_A:		MACRO 
			LD L, A 
			ADD A, A
			SBC A, A 
			LD H, A		
			ENDM

ADD_HL_A:		MACRO 
			ADD A, L
			LD L,A 
			JR NC, .S1
			INC H 	
.S1			;			
			ENDM 

ADD_DE_A:		MACRO 
			ADD A, E 
			LD E, A 
			JR NC, .S1
			INC D 
.S1			;
			ENDM

ADD_BC_A:		MACRO
			ADD A,C 
			LD C, A 
			JR NC, .S1
			INC B 
.S1			;
			ENDM 

ADD_BC_A_SIGNED:	MACRO
			OR A 
			JP P,.S1
			DEC B
.S1			ADD A, C  
			LD C, A 
			ADC A, B 
			SUB C 
			LD B, A 
			ENDM 

ADD_DE_A_SIGNED:	MACRO
			OR A 
			JP P, .S1
			DEC D
.S1			ADD A, E 
			LD E, A 
			ADC A, D 
			SUB E 
			LD D, A 
			ENDM 

ADD_HL_A_SIGNED:	MACRO
			OR A 
			JP P, .S1
			DEC H
.S1			ADD A, L  
			LD L, A 
			ADC A, H 
			SUB L 
			LD H, A 
			ENDM 

SUB_HL_BC:		MACRO	
			OR A 
			SBC HL,BC
			ENDM

SUB_HL_DE:		MACRO 
			OR A 
			SBC HL,DE 
			ENDM 
