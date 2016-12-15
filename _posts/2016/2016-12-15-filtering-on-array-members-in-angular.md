---
layout: post
title: "Filtering on Array Members in Angular"
summary: "When using filters with ng-repeat, filtering items based on child array members is a super useful trick."
comments: true
---

If you use Angular, and have used `ng-repeat` any, you probably know that you can filter the set that's being iterated through, using a filter in the `ng-repeat` expression. For example, let's say you've got a list of employees, and you want to be able filter that list, only seeing employees that work in a certain department. Let's look at how we'd do that in Angular:

<p data-height="265" data-theme-id="0" data-slug-hash="ObaEaj" data-default-tab="html,result" data-user="jwd2a" data-embed-version="2" data-pen-title="Angular Filtering" class="codepen">See the Pen <a href="http://codepen.io/jwd2a/pen/ObaEaj/">Angular Filtering</a> by Justin Davis (<a href="http://codepen.io/jwd2a">@jwd2a</a>) on <a href="http://codepen.io">CodePen</a>.</p>
<script async src="https://production-assets.codepen.io/assets/embed/ei.js"></script>

Easy enough. We're using the `filter:{'department':dept}` bit that comes after `ng-repeat` to filter the array that's being iterated, in real time. The syntax we're using here assures we're matching just on the `department` property, and asking it to match `dept`, which corresponds to the `ng-model` used in our input.

But, what if our array of items was more complicated? What if each employee had multiple departments, and those departments were objects with all kinds of information. How can we filter on that?

Let's take another example. We've got a list of employees, and each employee can belong to several departments. Each department has a name, a floor, and a description. What if we want to get all the employees that work in `engineering` now?

Luckily, this kind of deep filtering is a piece of cake in Angular. We can use a similar syntax to [mongo](https://docs.mongodb.com/v3.2/tutorial/query-documents/#specify-conditions-using-query-operators), and simply specify the path we want to match on. Check the example:

<p data-height="265" data-theme-id="0" data-slug-hash="VmVdNj" data-default-tab="result" data-user="jwd2a" data-embed-version="2" data-pen-title="Angular Deep Array Filtering" class="codepen">See the Pen <a href="http://codepen.io/jwd2a/pen/VmVdNj/">Angular Deep Array Filtering</a> by Justin Davis (<a href="http://codepen.io/jwd2a">@jwd2a</a>) on <a href="http://codepen.io">CodePen</a>.</p>
<script async src="https://production-assets.codepen.io/assets/embed/ei.js"></script>

Here, we're setting up our filter like this: `filter:{'departments': {'name': dept}}`, which lets us find only the objects in the department array with the `name` that matches. Because we're specific on how we write this path, it won't match on things we don't want it to, like descriptions that have the same word.  

Angular makes filtering like this super easy, and allow you to modify the dataset without writing custom filters or doing anything terribly complex. 

Hope this helps you streamline your UI and put more power into your filtering!
