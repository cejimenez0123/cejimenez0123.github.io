---
layout: post
title:      "Scraping Websites and Object Oriented Programming"
date:       2019-12-08 14:26:30 -0500
permalink:  scraping_websites_and_object_oriented_programming
---


I took a long road to get to where I am now with my code. Improving my coding abilities along the way and learning for what was around me. It got me to where I am now creating my first CLI Data gem. I had to use object orientation, scraping, and array/hash manipulation to make it.

The biggest hurdle for me was getting started. Where do I begin because I had a grasp of scraping, and if..else statements but I hadn't brought them all together yet until now. I had a rough start installing the studio, but it got done with help from friends. I took on the simplest task first and then move forward from there. Increasing in complexity the further I went.

The first thing I did for the gem was to create a class that would be the object in this case museums. I listed the goals for information I would need to scrape from the website. Creating an attr_accessor for all the adjectives that would describe my object museum. It needs the fundamentals. In needs a name, but also because it is a museum it needs a location and information on the museum. I knew I needed to retrieve the information with the scraper. 

Building the scraper I didn't know how to start. I went back to previous labs, and other examples of scraping were none provided a decent structure for what I wanted to do. Leading me further away from my goal. I had to use nokogiri and open-uri. It sounds simple, and it was once I learned it. 
`def scrape
        base_url = "https://www.any.com"
        html = open("#{base_url}#{@page}")
        @doc = Nokogiri::HTML(html)
    end`
        The reason it works, and this is was the best way in my case was because it is a very malleable piece of code. The base_url doesn't change, but I would be scraping from multiple pages. It made sense to me to make an instance variable because @page would be a URL extension for base_url. @page would change depending on the instance. This is, in contrast, simply being 'page.' Page with @ allows for the url extension to be reached in between methods. I needed the capability because otherwise, the code would be more complicated than it needed to be. I remembered DRY(Don't repeat yourself), but I also remember a podcast that said increasing complexity creates more possibility for error. I kept it in mind throughout my coding.
        
        I would often find myself writing code. I was frustrated not getting the result that wanted. When the way to get to the solution was to strip everything that appears I wasn't sure I needed. I worked with what I needed to. I spent the longest time using find iterator to find the same instance within the "has many" object that is within Museum.all. Museum.all is equal to self.all in the code. Museum.all is a class array that had been storing all the instances. I would try to look through it, code with it, but I can't find the answer I wanted. I'm not scared of starting over. I deleted what I had been working on and remembered what had been storing the information of the object within itself. I didn't need to find it was already there. I placed the instance as an argument within the method. We could then reach the URL for the specific instance. It then can be script when the URL is stored in @page.
        
        Scraping itself was also a big hurdle, I'm only the beginning of learning of CSS, but I already feel I am way more ahead. A great resource was www.w3schools.com/cssref/css_selectors.asp. I was used to targeting but class, but class is too limiting for what I need to do. I had an issue with too many cooks and the kitchen when I sought help. Some people made the code too broad others made the code too specific. Broad would be targeting an article and the first p, to specific would be targeting the information using the method .children[i]. They both got the job done but it wasn't why I needed. I went back to CSS selectors. Before they seemed senseless. I couldn't see a clear cause and effect between a selector and its output. I used my brain and started experimenting cause I learn by doing and seeing it being done. I joined information together I saw that there were many CSS selectors. I had to use one.
        
        I used  [attribute^=value] where    a[href^="https"]. You can target with precision. In the example, we target 'a's with a href of https, but this can be applied to any attribute. It opened many doors and helped me solve the last steps in scraping.
        
        I had the information at my fingertips at this point. I had already been making the CLI. I got ahead of myself and made the CLI first, but I deleted it, so I could start again with the information I had now. The information would be stored in an object instance and the object themselves would be the key to learning more information about the object. 
        
        The CLI became a series of if..else statements. Trying to visualize the walkthrough with my code as I was coding. I learned I can't nest if...else within an if...else. I made separate methods. The CLI jumps in between methods as it walks a user through the gem. When I got it working getting results I wanted I also received a lack of information. I had to create contingencies for anything that can happen within the code. It was frustrating but I got it done. Especially once I stopped trying to do everything with my code and simply doing what my code was good at.
        
        Next, I want to add to the museum gem and build on top of it. I'd like it if my code could access outside web resources, for example, I want to teach my code to use google maps so I can give the user a choice of routes, and give the user there best options based on their location. There's more to learn and I'm looking forward to every bit of it.
