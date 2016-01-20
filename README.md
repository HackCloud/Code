# Code
; 2*a*b*c + 3 - c

extern	printf

extern	scanf

global	main

section	.text



main:

	
	push	ebp
	
	mov	ebp, esp
	
	push	c
	
	push	b
	
	push	a
	
	push	sfmt
	
	call	scanf
	
	add	esp, 12
	
	pop	ebp
	
	mov	eax, [a] ; eax = a
	
	mov	ebx, [b] ; ebx = b
	
	mul	ebx	 ; a*b

	mov	[a], eax ; a = a*b

	
	mov	ecx, [c] ; ecx = c
	
	mul	ecx	 ; a*c
	
	mov	[a], eax ; a = a*b*c


	
	mov 	[a], eax ; a = a*b*c
	
	imul	eax, 2	 ; a*2
	
	mov	[a], eax ; a = 2*a*b*c

	

	mov	[a], eax ; a = a*b*c
	
	add	eax, 3	 ; a + 3
	
	mov	[a], eax ; a*b*c + 3
	

	
	sub	eax, [c] ; a + 3 - c
	
	mov	[a], eax ; a*b*c + 3 - c



	
	push	ebp
	
	mov	ebp, esp
	
	push	dword[a]
	
	push	fmt
	call	
	printf
	add	esp, 8
	
	pop	ebp
	
	mov	eax, 8
	
ret



section	.data
	
	fmt:	db "Rezult is: %d", 10, 0
	
	sfmt:	db "%d %d %d", 0
	
	a:	dd 0
	
	b:	dd 0	
	
	c:	dd 0
