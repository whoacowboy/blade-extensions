---
---
#### Foreach / Break / Continue

Introduces loop data when using foreach, also break and continue are available.
{% highlight html %}

@foreach($stuff as $key => $val)
    $loop->index;       // int, zero based
    $loop->index1;      // int, starts at 1
    $loop->revindex;    // int
    $loop->revindex1;   // int
    $loop->first;       // bool
    $loop->last;        // bool
    $loop->even;        // bool
    $loop->odd;         // bool
    $loop->length;      // int

    @break

    @continue
@endforeach

{% endhighlight %}

Nesting loops is possible and gives access to the parent's loop using `$loop->parentLoop`

{% highlight html %}

@foreach($stuff as $key => $val)
    $loop->index;       // int, zero based

    @foreach($other as $name => $age)
        $loop->parentLoop->odd;

        @foreach($friends as $foo => $bar)
            $loop->parentLoop->index;
            $loop->parentLoop->parentLoop->index;
        @endforeach

    @endforeach

@endforeach

{% endhighlight %}