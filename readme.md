# emacs proxy 
emacs proxy is used to make the process of repeating HTTP requests more automated.
it depends on:
1. mitmproxy: to collect and repeat HTTP requests 
2. fastapi and uvicorn: to handle the backend stuff

## basic features 
most of the features in the emacs proxy are found in almost all other proxies 
but it enables for more automation and infinite customizations.

### repeat requests and history
basic repeat and preview requests from history are available, the difference is that I 
can directly repeat requests from history, and navigate through redirects.
there are commented lines in the request that are just after the method line,
those lines represent the connection URL that the request is supposed to be sent to.



https://github.com/user-attachments/assets/a7b3ae95-ec6b-4508-8516-08a2b7dfc987


request buffer support evaluating python expressions to be interpolated in-place when 
the request is to be sent.



https://github.com/user-attachments/assets/dc2fb4d5-f264-45dc-b3f3-f1d784f0797c


in the request buffer it only support single value data, meaning that anything that will
be interpolated must implement the __str__ method.

### marking and highlighting matched HTTP flows 
using custom python expressions I can filter, mark and search in HTTP flows.



https://github.com/user-attachments/assets/b8d1421c-1dcd-4028-ae52-471558b2a312



### compare requests and responses 
it also supports comparision between requests and responses using emacs builtin ediff.



### encoding and decoding HTTP content 
if you ever used burp, you might be familiar with an addon called hackvertor, that is 
very convenient to use when you want to encode or decode content on the fly.
there is also a https://github.com/gchq/CyberChef outside of burp, emacs proxy uses 
a version of cyberchef that is written in python called chepy https://github.com/securisec/chepy
that can be run from the cli.


https://github.com/user-attachments/assets/16750f27-426c-4534-9d72-3fb3ea603ff3



emacs proxy can integerate very well with tools that has CLI and TUI.

### preview the response in browser 

you can preview HTTP responses in the browser using emacs webkit pacakge 


https://github.com/user-attachments/assets/6df2b35f-83f5-4bd2-a59c-a228536cc59d




### intercepting and changing HTTP content 
you can intercept the requests and responses using custom headers that are 
sent to the proxy, the proxy doesn't send those headers with the request, they 
are only used as a means for commuincation with the proxy



https://github.com/user-attachments/assets/8ebcbbae-fd98-4fa0-8cf7-9187d83a587f




### automation parts 
#### fuzzing with simple python expression
using emacs org-mode buffers you can collect your requests in `src_blocks`
you can inject python code that evaluates to iterables to  generate your 
fuzzing data.



https://github.com/user-attachments/assets/8b7d0a7c-2c79-4981-b9ec-0193ab09315c


