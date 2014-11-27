---
---
### Set / Unset

{% highlight php %}

@macro('simple', $first, $second = 3, $what)
    $who = $first . $second;
    return $what . $who;
@endmacro

@domacro('simple', 'my age is', 3, 'patat')

@macro('gravatar', $email, $size = 32, $default = 'mm')
    return '<img src="http://www.gravatar.com/avatar/' . md5(strtolower(trim($email))) . '?s=' . $size . '&d=' . $default . '" alt="Avatar">';
@endmacro

@domacro('gravatar', 'info@radic.nl', 80)

{% endhighlight %}