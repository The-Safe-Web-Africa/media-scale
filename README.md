# Media-scale

### [ENGLISH]

Compare one article's visibility on social media to known event's visibility in its regional's reference media to put number of reactions into perspective.

## Motivation, use and purpose

When fighting disinformation, analyses and fact-checks produced often relay - when they are not based on - **figures to measure the impact of a content** on a given society. 

Among such data can be the number of reactions to said content, the number of comments it yields, or the number of times it has been shared.

However, this data us usually not **contrasted** nor compared. Rather than focusing on their quantitative aspect, we offer an alternative: to organize data according to a scale of relevance. Thus, in considering the topic of the content instead of how many times it was shared, one reaches a **qualitative scale of reference**.

In a spreadsheet (.csv file), the number of engagements (shares, likes and comments alike) generated by an article is linked to: 
- its region or country of origin,
- its source (main national newspapers),
- the date of its publication,
- its topic (title). 

Therefore, **quantitative data is both contextualized and put into perspective**, in a **clear and accessible** way.

The comparison can be done manually or with the exposed API.

## API

### Installation

Clone the repository then install dependencies:

	npm install

### Usage

Start the server:

	npm start
	
Then, the following API endpoint can be used to programmatically get articles with a comparable visibility:

#### GET media-scale/1.0/around

Returns posts with similar shares number for each major newspaper of the given region

##### Query parameters

| Name  | Required | Description | Example |
| ----- | -------- | ----------- | ------- |
| region | required | The region where article comparison has to be done. Country code in ISO 3166-1 alpha-2 | fr |
| shares | required | The number of shares to compare to. Integer > 0 | 8765 |




##### Example Request
	
	GET /media-scale/1.0/around?region=fr&shares=150000

##### Example Response

```
{
	"Le Monde": {
		"totalEngagements": "158000",
		"facebook": "148100",
		"twitter": "9600",
		"pinterest": "1",
		"reddit": "273",
		"country": "FR",
		"source": "Le Monde",
		"date": "2017-07-10",
		"title": "La sixième extinction de masse des animaux s’accélère",
		"url": "https://www.lemonde.fr/biodiversite/article/2017/07/10/la-sixieme-extinction-de-masse-des-animaux-s-accelere-de-maniere-dramatique_5158718_1652692.html"
	},
	"Le Figaro": {
		"totalEngagements": "152900",
		"facebook": "152100",
		"twitter": "780",
		"pinterest": "0",
		"reddit": "0",
		"country": "FR",
		"source": "Le Figaro",
		"date": "2018-10-22",
		"title": "Fraude : 1,7 million d'euros d'allocations sociales détournées vers la Roumanie",
		"url": "http://www.lefigaro.fr/social/2018/10/22/20011-20181022ARTFIG00138-un-reseau-detourne-17-million-d-euros-d-allocations-sociales.php"
	},
	…
}
```

- - - - - - -

# License

- The code for this software is distributed under the European Union Public Licence (EUPL) v1.2.

- Data in this repository are distributed under an ODC-BY 1.0 license. That means you are free to share (to copy, distribute and use the database), to Create (to produce works from the database), to Adapt (to modify, transform and build upon the database) as long as you attribute to *Office of the French Ambassador for Digital Affairs*.

Contact the author if you have any specific need or question regarding licensing.
