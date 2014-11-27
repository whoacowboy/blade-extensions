---
---
#### Blade view testing
Allows all assertion functions to run inside a view.

**ExampleTest.php**
{% highlight php %}
use Radic\BladeExtensions\Testing\BladeViewTestingTrait

class ExampleTest extends TestCase {

	public function setUp()
	{
	    parent::setUp();
	    $this->addTestAssertsBladeDirectives();

	    // When creating packages
	    View::addLocation(__DIR__ . '/views');
	}

    public function testViewOne()
    {
        View::make('viewone', array('testArray' => ['somevalue', 'aao']))->render();
    }
}

{% endhighlight %}

**views/viewone.blade.php**
{% highlight html %}
@assertTrue(is_array($testArray))
@assertArrayHasKey(0, $testArray)
@assertTrue($testArray[0]['index'] === 0)
// etc
{% endhighlight %}