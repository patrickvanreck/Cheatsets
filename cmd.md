[An A-Z Index of the Windows CMD command line](https://ss64.com/nt/)

[Windows_Batch_Scripting](https://en.wikibooks.org/wiki/Windows_Batch_Scripting)


@echo off

Comment

	REM this is a comment line
	:: this is another comment line

[Environmental variables](https://ss64.com/nt/syntax-variables.html)

Set variables 
	
	set name=Fabrice
	set name=Fabrice Feugang Kemegni #no space between variable=value

Set Commands

	set helloWold=echo hello humans
	set r=reset

Read set Values

	echo %name%
	%r% #calls reset that has been set above

SETLOCAL

	:: every variable declared here and at eof|exit
	ENDLOCAL | EXIT

	set here=%CD%
	cd %here%

@echo off|on 
	
	#hide/show path


Change PROMPT

	PROMPT value 

	$A  &           (Ampersand) 
	$B  |           (pipe) 
	$C  (           (Left parenthesis) 
	$D Current date 
	$E Escape code  (ASCII code 27) 
	$F  )           (Right parenthesis) 
	$G  >           (greater-than sign) 
	$H  Backspace   (erases previous character) 
	$L  <           (less-than sign) 
	$M  Display the remote name for Network drives
	$N  Current drive 
	$P  Current drive and path 
	$Q  =           (equal sign) 
	$S              (space) 
	$T  Current time 
	$V  Windows NT version number 
	$_  Carriage return and linefeed 
	$$  $           (dollar sign)
	$+  Will display plus signs (+) one for each level of the PUSHD directory stack

Functions



String processing

	set a=abcd
	echo %a:~0,1% =>Result: a
	echo %a:~1,1% =>Result: b
	echo %a:~0,2% =>Result: ab
	echo %a:~1,2% =>Result: bc
	echo %a:~1%   =>Result: bcd
	echo %a:~-1%  =>Result: d
	echo %a:~-2%  =>Result: cd
	echo %a:~0,-2% =>Result: ab
	echo %a:~0,-1% =>Result: abc
	echo %a:~1,-1% =>Result: bc

<<<<<<< HEAD
## Sample programs

Read filename from stdin and delete file GOTO

	@ECHO OFF

	:prompt
	::Clear the value of filename ready for use.
	SET filename=
	SET /P filename=Enter filename to delete (q to quit): 

	IF EXIST %filename% (
	DEL /P %filename%
	GOTO prompt
	)
	IF /I "%filename%"=="q" GOTO :door

	::By this point an error must have occurred as all
	::the correct entries have already been dealt with.
	ECHO.ERROR: Incorrect entry!
	GOTO prompt

	:door
	exit

=======

Loop

	for /L %%i in (1,1,10) do (
  		echo %%i
	)

functions
		
	# batfile.bat 2 5 => 32
    call :raiseToPower %1 %2
    echo "%1 raised to the power %2 is: %raiseToPowerOutput%" 
    goto :door

    :raiseToPower
    setlocal
        set sum=%1
        set power=%2

        for /L %%i in (1,1,%power%) do (
            set /a sum=sum * %1
        )

    endlocal & set raiseToPowerOutput=%sum%
    goto :eof
    :door
    pause
    exit
	
	
	# return the input trippled
	call :trippe resultOfTripple=3 //resultOfTripple 3, resultOfTripple:3 
    echo %resultOfTripple%
    goto :eof

    :trippe
        set /a %1=%2 *3
    exit /b
	
>>>>>>> 381a5483de24d04e1c094e891396b95620e112a0