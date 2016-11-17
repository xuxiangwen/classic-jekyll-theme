# Classic-Jekyll-Theme v1.3.1

Welcome to Classic-Jekyll-Theme. This theme centers around one of the most used website structures on the web. A banner, navigation menu, (up to) three columns and a footer. The design is fully responsive for three different screen widths: wide, medium and narrow. It is probably best shown in an example:

Wide:

![wide-layout](http://balancingrock.nl/img/classic-jekyll-theme-wide.png)

Medium:

![medium-left-layout](http://balancingrock.nl/img/classic-jekyll-theme-medium-left.png)

Narrow:

![narrow-layout](http://balancingrock.nl/img/classic-jekyll-theme-narrow.png)

The columns are called Primary (blue), Secondary (grey) and Tertiary (pink). In the above layouts the secondary column is on the left side. If it had been on the right side, the medium layout would have looked like this:

![medium-right-layout](http://balancingrock.nl/img/classic-jekyll-theme-medium-right.png)

The menu bar (in yellow) is always deployed in the wide layout. In the medium and narrow layout the menu bar is shown in the deployed state. When not deployed, a menu-item symbol is shown in the banner that switches the menu between deployed and not.

An example screenshot:

![example](http://balancingrock.nl/img/classic-jekyll-theme-screenshot-half.png)

Other features:

- __Navigation bar__ is created automatically from the available pages when these have the proper YAML frontmatter. The navigation bar contains the top level menu items, while the submenu items show up as a drop-down menu when the cursor hovers over the corresponding menu item.

- __Category pages__ are created semi-automatically; the web designer has to identify the categories for inclusion, but the menu entry and category pages are created automatically.

- __Cookies policy__ for european users is included by default. It can be easily disabled for non-european websites though.

- __Language customization__ (not multi-language support!).

- __Icon__ support for an icon in the upper left corner of the site.

- __Background images__ and __Background color__ settings for major site elements.

You can get it from [github](https://github.com/Swiftrien/classic-jekyll-theme) or [rubygems](https://rubygems.org/gems/classic-jekyll-theme).

Subscribe to news about this theme (be informed of new releases) by sending a mail to: rien@balancingrock.nl with the subject "classic".

Like to help out?

You can support further development of this theme, or just say 'thank you' via paypal by donating to sales@balancingrock.nl or wire bitcoins to address: 1GacSREBxPy1yskLMc9de2nofNv2SNdwqH

Suggested donation for personal websites is the price of a good cup of coffee: $4

Suggested donation for commercial sites is the price of a good meal: $20

## Installation & setup

Install it as:

    $ sudo gem install classic-jekyll-theme

Create a new project:

	$ jekyll new great-site
	
Change the directory:

	$ cd great-site
	
Change in the Gemfile:

	From `gem "minima", "~> 2.0"` to `gem "classic-jekyll-theme", "~>1.3.0"`

Change in the _config.yml:

	From `theme: minima` to `theme: classic-jekyll-theme`

Delete the file `about.md`:

	$ rm about.md

It is possible to start the jekyll server now:

	$ jekyll serve
	
Then the site will show up at `localhost:4000`.

To add sample content that illustrates how pages and categories are implemented, copy the folder `pages` from the gem to the current project. On MacOS the gems are located in: `Library/Ruby/Gems/<version>/gems/classic-jekyll-theme-<version>`. Replace the version's with the appropriate numbers (note: these are two different unrelated version numbers). These pages not only contain examples, but also some information about using the theme.

## Configuration

The theme is configured in:

- `_sass/classic-jekyll-theme.scss`: For the graphical elements.
- `_data/setup.yml`: For general layout and widget configuration.
- `_data/text-for.yml`: For language customization of the textual elements of the theme.

### _sass/classic-jekyll-theme.scss

The default `main.scss` file has been emptied. Hence all CSS configuration is done in the theme sass file.

### setup.yml

The following values are configurable:

- secondary_column:

	Controls the placing of the secondary column on either the `left` side, the `right` side or `none` at all.

	When the secondary column is present its contents is taken from the file: `_includes/secondary-column.html`

- tertiary_column:

	Controls the presence of the tertiary column, either `present` or `none`.

	When the tertiary column is present its contents is taken from the file: `_includes/tertiary-column.html`

- number-of-posts-on-home-page:

	By default set to 5, thus 5 posts will be shown in full on the home page.
	
- number-of-recent-posts-in-widget:

	The number of posts (titles) that will appear in the "Recent" widget.

- enable-cookies-policy:
 
	`yes` to enable the cookies warning, `no` to disable. The cookies warning is from [Silktide](http://silktide.com/cookieconsent), distributed under the MIT license.

### text-for.yml

Some of the text elements in the theme can be translated with the following definitions:

	If a definition is absent, the default shown will be used.

	`tHome: Home` # Menu item
	
	`tPosts: Posts` # Title on home page
	
	`tCategories: Categories` # Menu item
	
	`tCategory: Category` # Title on categories page
	
	`tNoBlogpostFound: No blogposts found for this category` # Message on category page if no posts have been found
	
	`tMore: more` # Continuation text for abbreviated posts on a category page
	
	`tTags: Tags` # Tag label on category page
	
	`tRecent: Recent` # Title on recent posts widget
	
	`tSocialMediaResources: Social Media & Resources` # Part title of social media widget
	
	`tSubscribe: Subscribe` # Title of subscription widget

	`tUsesCookies: This site uses cookies` # Cookie warning message
	
	`tCookieOk: OK` # Text for OK button
	
	`tMoreInfo: More info` # More cookie info text

## Recommendation

Typically you will need to copy some files from the gem iteself to the project (web site) directory. The most common files are:

- `_sass/classic-jekyll-theme.scss` for configuration
- `_data/setup.yml` for configuration
- `_data/text-for.yml` for configuration
- `_includes/secondary-column.html` for the secondary column contents
- `_includes/tertiary-column.html` for the tertiary column contents

These files can be found in the gem directory. On macOS this directory is located at: `Library/Ruby/Gems/<version>/gems/classic-jekyll-theme-<version>`. When you copy these files, make sure they are in the same relative directory as in the gem itself.

Besides the above mentioned files you should avoid making changes to the files provided in the gem. The more changes you make, the more difficult it will become to upgrade. Instead of chaning a file, include a new file that contains the stuff you want and include that file.

For example, if you need to add to the SASS files, create a new file and include that at the end of `_sass/classic-jekyll-theme.scss`.

## Creating Posts

Posting is done exactly like in the standard Jekyll environment.

## Creating a Category Page

A category page is a page that contains links to all posts published in that category.

To kick-off the creation of a category page, create a new page and include the following front matter:

	---
	layout: category-page
	title: classic
	---

The rest of the page can remain empty, it will be automatically created. The _category-page_ triggers the generation of a category page. The _title_ is the category the page is created for. The category (and thus also the _title_) are case sensitive.

## Creating Pages for the menu bar

To create a page that must be included in the menu bar, add the following front matter to that page:

	---
	...
	menuInclude: yes
	menuLink: yes
	menuTopTitle: Classic
	menuTopIndex: 2
	menuSubTitle: "About Pages"
	menuSubIndex: 4
	---

- menuInclude: Set to "yes" to consider this page for a navigation bar menu item.
- menuLink: Set to 'no' to disable a link creation from the navigation bar to this page. However the menu title or subtitle will be included. This allows the ordering of menu items that do not have an associated page. The default behaviour assumes 'yes'. So not including this tag will create a link. Note: This allows ordering of top level menu items. For submenu items this probably only makes sense if some kind of "divider" must be shown. Otherwise showing a submenu item without a link will probably confuse users.
- menuTopTitle: The title of the menu item in the navigation bar. When used in conjunction with a menuSubTitle, this will be the title of the menu item to which this submenu item will be added in the drop down menu. 
- menuTopIndex: The place of the title within the menu bar. Lower numbers will be to the left of higher numbers. Be aware that the "Home" menu item will always be first and the "Categories" will always be last.
- menuSubTitle: The title of the submenu item in the drop down menu.
- menuSubIndex: The place of the submenu item within the dropdown menu. Lower numbers will go above higher numbers. This theme only sorts on menuIndex numbers, not on other properties.

For a consistent user experience in the narrow layout, it is recommened not to link pages to top level menu items if these menu items have a drop-down submenu.

## History

Release 0.2.6

- Inital version (before this I was only getting acquainted with the gem-publishing mechanism)

Release 1.0.0

- Fixed a problem with navigation menu generation. (Insufficient control over menu item placement)

Release 1.0.1

- Fixed some info in this readme file and in the example pages.

Release 1.1.0

- Added language customization for default theme elements in the `_config.yml` file

Release 1.1.1

- Added clarification to upgrade information.

Release 1.2.0

- Added facilities for background images.
- Added option for an icon on the top-left side of the site.
- Fixed a problem where the tertiary column divider was not removed for medium layout.

Release 1.2.1

- Fixed problem with Icon placement.

Release 1.2.2

- Fixed problem with site title shifting when a background was used.
- Now allows absolute fixing of banner height.

Release 1.2.3

- Faster generation of site
- Menu item 'Categories' will only be included if categorie pages are requested by the designer.
- Categories pages submenu is now alphabetical.

Release 1.3.0

- Removed theme specific configuration from the `_config.yml` file into `_data/setup.yml` and `_data/text-for.yml`.

Release 1.3.1

- Quick fix for problem introduced in 1.3.0

## Upgrade information

### from 0.2.6 to 1.0.0

#### Page creation

The page creation YAML matter has changed. The old tags did not give full control over the menu buildup, the new tags do.

	Old: menuInclude
	New: menuInclude

No changes, works as before.<br><br>

	Old: -
	New: menuLink true|false

A new option that controls if a menu title has a link to a page. The default value is 'true' so when this tag is not included, a link to the page will be created. If set to 'false', then the menu item will show up in the specified place, but will not be linked to a page. Use this to order menu items that have a drop-down menu but do not have a page by itself.<br><br>

	Old: menuTitle
	New: menuTopTitle
	New: menuSubTitle

Specifies the string to be used for the menu item.<br><br>

	Old: subMenuFrom
	New: menuTopTitle

Specifies the menu item from which this is a submenu item.<br><br>

	Old: menuIndex
	New: menuTopIndex
	New: menuSubIndex
	
The index for a menu item. If not present, the menu ordering is undetermined. If only a part of the pages have this item then the menu items of the pages that do not have this item specified will be included first. If multiple specifications exist, then the highest number overrides the lower numbers. Like before, a lower number goes to the left -or on top- of the higher number.

### from 1.0.0 (and later) to 1.1.1

- Update the version number in the `Gemfile`

### from 1.1.1 to 1.2.0

- If changes were made to `_sass/classic-jekyll-theme.scss` then this file must be replaced with the new version that comes with this release and the changes must be re-applied. Note that background color setting has changed slightly.
- As always, update the version number in the `Gemfile`

### from 1.2.0 to 1.2.1

- Replace the 'initial' values in `_sass/classic-jekyll-theme.scss` for the backgrounds with 'none'.
- The icon size (width and height) values are no longer used and can be removed.
- As always, update the version number in the `Gemfile`

### from 1.2.1 to 1.2.2

- The banner height settings in `_sass/classic-jekyll-theme.scss` are no longer "minimum" specifications but absolute specifications and therefore have been renamed from `<layout-size>-minimum-banner-height` to `<layout-size>-banner-height`.
- As always, update the version number in the `Gemfile`

### from 1.2.2 to 1.2.3

- Update the version number in the `Gemfile`

### from 1.2.3 to 1.3.0

- Remove the classic-jekyll-theme configurations from the `_config.yml` file, and reapply any changes made to either `_data/setup.yml` and/or `_data/text-for.yml` as required.
- As always, update the version number in the `Gemfile`

### from 1.3.0 to 1.3.1

- Update the version number in the `Gemfile`

## Known problems (need your help)

There is some odd behaviour in the navigation bar that I have not been able to nail down yet. It has to do with the space between top level menu items. There is some additional space that I am not able to trace down. For those who like a puzzle: there is some space around a ".navbanner-menu ul li" that has no obvious source. Please let me know if you happen to find where it comes from. (rien@balancingrock.nl)

## Feedback

Comments, bug reports, feature requests and improvements are eagerly anticipated via email: rien@balancingrock.nl.

## License

The theme is available as open source under the terms of the [MIT License](http://opensource.org/licenses/MIT).

