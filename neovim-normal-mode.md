# NEOVIM NORMAL MODE

## Search for Selected Text
Yank it, bring up cmd mode, paste it
y :/<C-R>"/

## Movement
### Up/down half-page scroll
<c-u> and <c-d>

; repeat
, reverse

i inside

## Like di( delete inside parenthesis
cit      Change inside tag <h1>test</h1>

a around

## Like ca' change around quotes
cb<            Like change block <> could change whole html element

## {action} to character
dt. delete to . but not including it
ct. change to . but not including it

# Make uppercase
~

# Make # of characters uppercase
3g~

# Find file or folder and edit
use tab key at end
`:e **/mydir/services/`

# Indent Number of lines
# often the indent won't show visually until you press your next key like 'j'
`5>>`

# Paste and Match indent
`]p`

# Increase inner block indent
`>i{`

# Re-indent entire file
`gg=G`

# Copy Entire File to Clipboard
`:%yt`

# Go to first char of line
0

# Name terminal window
`:file term-1`
