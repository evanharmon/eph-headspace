# CSS BOOSTRAP2
12 Columns Total - span and offsets must always total 12

## Span
number of columns wide for an object
example: input half of screen
```
<div class="row">
<div class="span6"><input /></div>
</div>
```

## Offset
horizontally aligned placement
example: input 6 span wide centered -  offset3 + span6 + offset3 = 12
```
<div class="row">
<div class="span6 offset3"><input /></div>
</div>
```

## Two Column Layout
```
<div class="row">
<div class="span6"></div>
<div class="span6"></div>
</div>
```

## Centered Two Column Layout
```
<div class="row">
<div class="span4 offset1"></div>
<div class="span4 offset1"></div>
</div>
```
