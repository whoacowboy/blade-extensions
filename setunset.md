---
---
#### Set / Unset

Setting and unsetting of variables

```php
@set('newvar', 'value')
{{ $newvar }} // echo's "value"


// All these combinations work
@set('mams', 'mamsVal')
@unset($mams)

@set($mams, 'childs');
@unset('mams');
```