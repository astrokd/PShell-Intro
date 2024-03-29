# Introduction to PowerShell

## What is PowerShell

PowerShell is an interactive object based shell that accepts and returns objects.  It is meant primarily for IT professionals to automate tasks in the Windows environment.  It is also a scripting language built on the .NET CLR.  It is open source and cross-platform.  It comes with a standard set of commands, in text referred to as cmdlets (in speech command-lets), the naming of these cmdlets follow a verb-noun format.

<details>
    <summary> <b>What does this mean?</b> </summary>

Interactive, meaning the shell reads and writes to the command line.  The user inputs commands and the shell outputs the results of the commands back to the command line.  This makes it like bash, the Python shell, or Windows old command line.  It is a .NET Framework application.

Object based, means you input commands and all output is returned as .NET objects.  In addition to that, these objects can be read by other PowerShell cmdlets.  Objects are not strings of text, or numbers but are made of both and other objects, essentially objects are data.

PowerShell was originally adopted by MicroSoft to replace the windows command line and be an automation solution for Windows.  Therefore it has a lot of commands related to Windows subsystems and environment, everything you can do in Windows dialogs can be done through PowerShell.

Aside from running single line commands that return output you can also run scripts that are several lines of commands.  The .NET CLR or .NET Common Language Runtime this allows PowerShell to output .NET objects.

PowerShell is open source, anyone can see its underlying code, make changes through an official change process, or submit issues and suggestions.  The open source code repository can be found here, [Github PowerShell repo](https://github.com/PowerShell/PowerShell).  And it is cross-platform, meaning there are versions of it for other OS's besides Windows.  Currently this is macOS and Linux.

PowerShell Cmdlets follow a Verb-Noun pattern like ‘Get’ or ‘Set’ for a verb and ‘Variable’ for a noun.  So using `Get-Variable` you can get a list of variables and with `Set-Variable` you can get  set a variable.

</details>
<br/>

### Learning Resources

A lot of information on using and learning PowerShell can be found on [MicroSofts main PowerShell Page](https://docs.microsoft.com/en-us/powershell/) and PowerShell Community sites like [PowerShell.org](https://powershell.org/).  But, one of the easiest and most useful places is in PowewrShell itself.

Using the `Get-Help` cmdlet you can find help on PowerShell cmdlets and other topics.  For example `Get-Help <cmdlet-name>` can give you help on a specific cmdlet/function or `Get-Help About_<topic>` for help on concept or language element.  And if you search the the internet for a specific cmdlet you will useful information.

Aside from `Get-Help` there are a few other cmdlets that will help you learn how PowerShell works and what your PowerShell version and install on any particular system might have available to it.

<details>
    <summary><b>Useful CmdLets aside from</b> <code>Get-Help</code>.</summary>

1. `Get-Command` Gets the available cmdlets and functions on a system.
    1. Default alias: gcm
2. `Get-Variable`. Gets the variables set on a system.
    1. Default alias: gv
3. `Get-Alias`. Gets the alias’s set on system.
    1. Default alias: gal
4. `Get-Verb`. Gets the available cmdlets verbs on system.
    1. or just `verb`

</details>
<br/>

### The Pipeline

The Pipeline in PowerShell is what is refered to when you chain cmdlets togther in complex chain.  The output of the first cmdlet is the input to the next.  The cmdlets are separated by the pipe character, `|`.

For example: ` Command-1 | Command-2 | Command-3 `

PowerShell cmdlets output and accept objects in their operation.  So you could use a Get- command to get data, then the Where-Object to filter the data, Sort-Object to sort it, and a Format command to format it.

For example: ` Get-ChildItem -Path *.txt | Where-Object {$_.length -gt 10000} | Sort-Object -Property length | Format-Table -Property name, length `

The above example gets txt files where the length is greater than 10000, then sorts them by length and formats them in a table with name and length.


