### First assignment

#### Important notes
* Jekyll does not support upstream variable propagation, so I have to have the same navbar in each layout
* Pagination plugin does not work with multiple _posts files in the project, so I had to add manual include and markdownify for web-publishing posts

##### Our task was to implement static web site using jekyll.

###### We had to use at least 3 layouts as well as:
* at least 5 variables
* collections or data files
* at least 5 filters or tags
* at least 1 plugin (except for pagination)

###### Layouts are present in _layouts sub-folder
* main.html - Main layout with all important imports
* info.html - Layout for Homepage and about-me page
* single-content.html - Layout for my-music and my-places
* with-posts.html - Layout for projects and web-publishing

###### Variables are used in _config.yml, in the index.html files and in the markdown files

##### Collections and data files use yml format. They are stored in _data folder
{% highlight yml %}
my-locations/locations.yml: Important places in users life
    - title: "Home"
      url: "#home"
      location:
        latitude: 48.157115
        longitude: 17.055694
    - title: "School"
      url: "#School"
      location:
        latitude: 48.1530717
        longitude: 17.0678752
    - title: "Work"
      url: "#work"
      location:
        latitude: 48.15945
        longitude: 17.127080
    - title: "Permanent residence"
      url : "#residence"
      location:
        latitude: 48.209250
        longitude: 17.151095
aboutMe.yml: General info about the user
    name:
      first: "Michal"
      last: "Dolnák"
    birth:
      day: "27"
      month: "05"
      year: "1996"
    birthplace: "Bratislava"
    address:
      street: "Kubačova 7"
      postalCode: "831 06"
      city: "Bratislava"
    status: "Single"
    educations:
      - faculty: "Faculty of Informatics and Information technologies of the Slovak University of Technology Bratislava"
        program: "Informatics"
        since: "2014"
        until: "yet"
        descriptions:
          - line: "Focused on data structures and algorithms, design of information systems and software engineering"
      - faculty: "Gymnasium Hubeného 23 in Bratislava"
        program: "Foreign languages"
        since: "2006"
        until: "2014"
        descriptions:
          - line: "Focused on English and German languages"
    workExperiences:
      - name: "Java Junior developer"
        employer: "Creative Web s.r.o."
        since: "06/2016"
        until: "yet"
        descriptions:
          - line: "Development of web applications using Java and Groovy in framework Grails"
          - line: "Implementation of automated tests in frameworks Spock and Geb"
          - line: "Frontend development in Angular2 using HTML, CSS, typescript and javascript"
          - line: "Additional used technologies include PostgreSql, Hibernate, Selenium, lxc containers"
      - name: "Administration assistant"
        employer: "Global Blue Slovakia"
        since: "07/2015"
        until: "09/2015"
        descriptions:
          - line: "Writing various data into internal systems using Access databases and Excel"
          - line: "Validation of received forms/documents with received data"
          - line: "Forms scanning"
          - line: "Forms archiving"
    activities:
      - name: "IAESTE Slovakia"
        position: "Member of local committee"
        since: "04/2016"
        until: "yet"
        descriptions:
              - line: "Development of new web applications in Spring, Angular 2 and Grails"
              - line: "Data exports, support and monitoring of existing IT systems"
              - line: "Organization planning of tournaments for the members of the local committee"
              - line: "Participation in the organization planning of carrier fairs, workshops and summer program for internship students"
    computerSkills:
      - name: "Java"
        level: "advanced"
      - name: "Groovy"
        level: "advanced"
      - name: "HTML, CSS"
        level: "advanced"
      - name: "javascript, typescript"
        level: "advanced"
      - name: "C, C++"
        level: "basic"
    certificates:
      - name: "IELTS-2013 exam, score 7.5 (level C1-C2)"
      - name: "Driving license category B"
    languages:
      - name: "Slovak"
        level: "C2"
      - name: "English"
        level: "C1"
      - name: "German"
        level: "A2"
    contact:
      email: "dolnakmichal@gmail.com"
      telephone: "+421908021705"
pages.yml: Links in navbar
- text: "Home"
  url: "/"
- text: "About me"
  url: "/about-me/"
- text: "Projects"
  url: "/projects/"
- text: "Web publishing"
  url: "/web-publishing/"
- text: "My places"
  url: "/my-places/"
- text: "My music"
  url: "/my-music/"
{% endhighlight %}
##### Filters and tags:
{% highlight yml %}
- for tag: used throughout the site
- if tag: used throughout the site
- include tag: mainly used in layouts
- sort filter: used in homepage
- where filter: used in homepage
- assign and remove: used in navbar
- capture and markdownify: used in
- and many more
{% endhighlight %}
##### Plugins used:
* 1. [jekyll-youtube-plugin](https://gist.github.com/joelverhagen/1805814)
* 2. [jekyll-googlemaps-plugin](https://github.com/ayastreb/jekyll-maps)
* 3. [jekyll-paginate-plugin](https://github.com/jekyll/jekyll-paginate)
##### Only pagination plugin works on github pages.


