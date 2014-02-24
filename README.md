# credits.json

Machine readable data format that describes the creators of a website.

## Wait a minute, isn't this humans.txt?

Not quite. Humans.txt is a great effort but it's not easily machine parsable[0], in fact, being easily machine parsable defeats the purpose of humans.txt (that is, making it easy for humans to read!).

[0] - Just have a look at the differences between [Google's](https://www.google.com/humans.txt), [Github's](https://www.github.com/humans.txt) and [humanstxt.org's](http://humanstxt.org/humans.txt)

## Ok, but why?

With a credits.json file it makes it easy to track what websites you've built over the internet, not only that, you can proove you worked on the site because the credits.json actually exists on the site that you build. Once the credits.json is in place, it's easy to automatically pull information from it. This makes it easy to generate portfolio websites and build a history of the work you've done.

## Who's making this? Who's in control of it?

At the moment it's just two of us but the purpose of creating this repository is to get input from everyone on what the credits.json format should include. If you've got some ideas or suggestions, please fork, implement and make a pull request so everyone can discuss the changes. As well as an open discussion that will shape the format, it is also licensed using the Apache License.

## Ok, show me what it looks like

```
{
  version: "0.1",
  created_at: "2014-02-22",
  client: {
    client: "todo"
  },
  organisations: [
    {
      name: "The Super Design Agency",
      location: "123 Street, My City, A Country",
      homepage: "http://www.example.com",
      people: [
        {
          name: "John Doe",
          email: "$2a$10$JGDDOBPPnuUiwb/OSHL4du9NwbHb/ZygFJm/SXk/wl1b9NoxlHQAO",
          roles: ['Design', 'Front end development'],
          location: "123 Street, My City, A Country",
          homepage: "http://www.example.com"
        }
      ]
    }
  ],
  people: [
    {
      name: "Jane Doe",
      email: "$2a$10$Rs2//C.zRkfYeXiZwp.vuutbkKV6mxR5Xnpo8D/oShsrj9VTIf/Mm",
      roles: ['Backend end development'],
      location: "123 Street, My City, A Country",
      homepage: "http://www.example.com"
    }
  ]
}
```

Let's explore the format in a bit more detail:

#### Version

```
{
  version: "0.1"
}
```

The credits.json format is versioned, at the moment we are arbitrarily at version 0.1. We will freeze the standard at 1.0 then begin work on version 2.0 when needed. 

#### Created at

```
{
  created_at: "0.1"
}
```

The date the credits.json file was created. This is generally the date the site went live and is useful for generating snapshots of the site over time.

#### Organisations

```
{
  name: "The Super Design Agency",
  location: "123 Street, My City, A Country",
  homepage: "http://www.example.com",
}
```

Two top level entities are allowed in the format, the first os which is Organisations. These represent the business entities that worked on the site for the **client**.

## More resources

* credits.json generator coming soon
* site portfolio website coming soon