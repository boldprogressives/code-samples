---
layout: base2
---

Checkboxes
----------

Take a look at a standard radio/checkbox code. You can break it down into three sections.

{% highlight html %}
<input type="checkbox" name="action_loves_ice_cream" value="true" id="ice-cream" /> 
<label for="ice-cream">I love ice cream</label>

<input type="checkbox" name="action_loves_pie" value="true" id="pie" />
<label for="ice-cream">I love pie</label>   
{% endhighlight %}

The &quot;name&quot; and the &quot;value&quot; are the parts of our code that get recorded into our database. Think of &quot;name&quot; as the question you&apos;re asking the member and &quot;value&quot; as the member&apos;s answer to the question. When you use checkboxes, a member can click as many as they want, and as long as they all have different &quot;names&quot; or different &quot;values&quot;, they&apos;ll all be recorded safely in the database.

To learn more about choosing a name, be sure to read the ActionKit/ActionFields Guidelines. (for example, names should ALWAYS start with the prefix action_; that&apos;s what tells the database it&apos;s time to start storing information.)


Radio Buttons
-------------

For questions where you want the member to only choose one answer (&quot;Do you want ice cream? Yes, No, Maybe&quot;), you should use radio inputs with the same name. This ensures that a user can only select one option at a time. (But the different inputs still need distinct values, or else we won&apos;t know which one they picked!)


{% highlight html %}
<input type="radio" name="action_syria_usaction" value="yes" id="usaction_yes" />
<label for="usaction_yes">Yes</label>
{% endhighlight %}

Note for both checkboxes and radio buttons, the &quot;id&quot; and &quot;label for&quot; attributes make it easier for our members to click on the different options. For easy setup, just squish together your &quot;name&quot; and &quot;value&quot; and make sure they&apos;re the same for &quot;id&quot; and &quot;label for&quot;. So if you have &quot;&lt;input name=&quot;great&quot; value=&quot;job&quot; /&gt;&quot;, then &quot;id&quot; and &quot;label for&quot; would be &quot;great_job&quot;. 

Radio Buttons
-------------

Q: Do you want ice cream?
{% highlight html %}
<input type="radio" name="action_icecream" value="yes" id="icecream_yes" />
<label for="icecream_yes">Yes</label>

<input type="radio" name="action_icecream" value="no" id="icecream_no" />
<label for="icecream_no">No</label>

<input type="radio" name="action_icecream" value="na" id="icecream_na" />
<label for="icecream_na">I don't know.</label>
{% endhighlight %}

Checkboxes
----------

Q: What kind of pizza toppings do you want to have on the pizza?
{% highlight html %}
<input type="checkbox" name="action_pizza_topping" value="pineapple" id="pizza_topping_pineapple" />
<label for="pizza_topping_pineapple">Pineapple</label>

<input type="checkbox" name="action_pizza_topping" value="pepperoni" id="pizza_topping_pepperoni" />
<label for="pizza_topping_pepperoni">Pepperoni</label>

<input type="checkbox" name="action_pizza_topping" value="tofu" id="pizza_topping_tofu" />
<label for="pizza_topping_tofu">Tofu</label>

<input type="checkbox" name="action_pizza_topping" value="mushrooms" id="pizza_topping_mushrooms" />
<label for="pizza_topping_mushrooms">Mushrooms</label>
{% endhighlight %}

Text
----

For this option, you can just copy and paste the below code and make the appropriate &quot;name&quot;.
{% highlight html %}
<textarea name="action_choose_a_name" rows="1" cols="15">Type your opinion</textarea>
{% endhighlight %}

Hidden option
-------------
To create a hidden option, include the onClick in the &lt;label&gt; section of your code. Make sure that it matches to a <div></div> where you will put the dropdown content. See below for code.

{% highlight html %}
<input type="radio" name="action_icecream" value="na" id="icecream_na" onClick="$('.hiddenoption_name_goes_here-div').toggle(500);"/>
<label for="icecream_na">I don't know.</label>

<div class="hiddenoption_name_goes_here-div" style="display: none;" />
Put your hidden option content here.
</div>
{% endhighlight %}

Page A/B
--------

You can read more on A/B tests here. Below is just a simple example of how to set up one on the page. Check out the HTML view of the introduction text in Step 2 of the sample page.
{% highlight html %}
<div class="ab ab-name=test ab-version=yes default">
  <p>This is A/B test option yes. Look at this cat!</p>
  <img src="http://i397.photobucket.com/albums/pp51/ls_yung/bth_cat.gif" align="center">
</div>

<div class="ab ab-name=test ab-version=no">
  <p>This is A/B test option no. There's no cat, but there's this awesome video!</p>
  <a href="http://www.youtube.com/watch?v=wR1L51_bEbk">http://www.youtube.com/watch?v=wR1L51_bEbk</a>
</div>
{% endhighlight %}
