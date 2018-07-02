# Right Prompt
RPROMPT=''

# User
%n

# Machine Name up to first .
%m

# Current Path
%c

# PWD with specific trailing components
%2/

# Current History Event Number
%h

# Full Host Name
%M

# Start / Stop Standout Mode
%S or %s

# Start / Stop Bold Mode
%B or %b

# Start / Stop Underline Mode
%U or %u

# Time of Day
%t, %@ # 12 hour format
%T # 24 hour format
%* # 24 hour with seconds

# Single `%'.
%%

# Dates
%d # Weekday in Day Format
%D #weekday in dd format
%w # month in Mon format
%y # year in yy format
%YY # year in yyyy format

# Colors
# Example %{\033[31m%}%m%{\033[0m%}
\030 # Black
\031 # Red
\032 # Green
\033 # Yellow
\034 # Blue
\035 # Magenta
\036 # Cyan
\037 # White

# Color Control
# Example %{\033[1;31m%}%m{\033[0m%}
0 # Normal
1 # Bold
2 # Normal Again
3 # Background Color
4 # Underline
5 # Blinking

# Clear to End of Line
%E

# Ternary Expression
%(x.true-text.false-text)
