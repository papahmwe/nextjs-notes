### Search Engine Optimization - SEO

- SEO is crucial for optimizing a website's visibility and ranking in search engine results.

- Prioritizing SEO can greatly impact the success of your website and its online presence.

- You can achieve several benefits, including:
  \
  (1) Increased organic traffic
  \
  (2) Enhanced user experience
  \
  (3) Credibility and trustworthiness
  \
  (4) Competitive advantage

  Note &rarr; Organic Traffic

  - the number of website visitors that come from unpaid search engine results (as opposed to paid results).

#### How do search engines work?

Search engines work three primary functions:

(1) Crawling
\
(2) Indexing
\
(3) Ranking

#### What is search engine crawling?

#### (1) Crawling

- the discovery process or the discovery of pages and links that lead to more pages
- send out a team of robots (known as crawlers or spiders) to find new and updated content
- Content can vary: it could be a webpage, an image, a video, a PDF, etc..; but regardless of the format, content is discovered by links

#### What is a search engine index?

#### (2) Indexing

- storing, analyzing, and organizing the content and connections between pages
- a part of a normal search engine process
- it makes sure people who are looking for information about your website or business can find your content

#### What is a search engine ranking?

#### (3) Ranking

- content's position on the search engine results pages (SERPs)
- it makes your website more visible

#### Search Systems in Next.js

- Search Systems have four main responsibilities:
  \
  (1) Crawling
  \
  (2) Indexing
  \
  (3) Rendering
  \
  (4) Ranking

- Crawling – the process of going through the Web and parsing the content in all websites. This is a massive task as there are over 350 million domains available.

- Indexing – finding places to store all of the data gathered during the crawling stage so it can be accessed.

- Rendering – executing any resources on the page such as JavaScript that might enhance the features and enrich content on the site. This process doesn't happen for all pages that are crawled and sometimes it happens before the content is actually indexed. Rendering might happen after indexing if there are no available resources to perform the task at the time.

- Ranking – querying data to craft relevant results pages based on user input. This is where the different ranking criteria are applied in Search engines to give users the best answer to fulfill their intent.

---

### API Endpoint

![API endpoint](assests/api-endpoint.png)

---

### Server Components vs Client Components in Next.js 13

- there are two environments where your application code can be rendered the client and the server

- server components are the default

- you need to add "use client" directive on top of the components you want to use as client components

- recommends using server components until you need to use client components

- state or hooks like useState(), useEffect(), useContext() or other client-side management solutions are only available on the client-side component

- to access browser-related things, like onClick events , window or browserAPI, you need to use the client component

  ![Server Components vs. Client Components](assests/component-comparison.webp)

---

### Routing in Next.js 13

- use file-based routing system which means that the routing is handled by the file system

- each folder in the app or page directory becomes a route and the folder name becomes the route's path

- no need for external packages or complex configurations

#### Dynamic Routes

- when you don't know the exact segment names ahead of time and want to create routes from dynamic data, you can use Dynamic Segments that are filled in at request time or prerendered at build time

- can be created by wrapping a folder's name in square brackets: [folderName] for example, [id] or [slug]

---

### Data Fetching

Next.js provides 3 choices for selecting how to fetch data;

1. Server Side Rendering (SSR)
2. Static Site Generation (SSG)
3. Incremental Static Generation (ISR)

#### 1. Server Side Rendering (SSR)

- Dynamic Rendering
- the content is always up to date
- don't store data, just call

#### 2. Static Site Generation (SSG)

- by default, next.js uses SSG
- automatically fetch data (data is fetched at build time)
- ideal for content that doesn't change frequently such as blog posts, documentation or marketing pages

#### 3. Incremental Static Generation (ISR)

- to create or update static pages
- combines the benefits of SSR and SSG for dynamic content in static sites

---

### Metadata

- Data about data

- Metadata is the abstract of the website's content and is used to attach a title, a description, and an image to the site.

- We can define Metadata in two ways: Static and Dynamic.

---

### React Hook

React Hook များသည် functional component တစ်ခုမှ ပြန်သုံးနိုင်သော အစိတ်အပိုင်းကို ခွဲထုတ်ရန် အသုံးပြုနိုင်သော JavaScript လုပ်ဆောင်ချက်များဖြစ်သည်။

#### useState( )

state များကို စီမံခန့်ခွဲရန်

useState() function က params နှစ်ခုပါမယ်။
(update လုပ်ရန်အတွက် stateful value နှင့် updater function)

- const [state, setState] = useState(initialState);

return အနေနဲ့ useState() function က တန်ဖိုး (state) နဲ့ အဲ့တန်ဖိုးကိုပြင်လို့ရတဲ့ function (setState) ကို ပြန်ပေးတယ်။

တန်ဖိုး (state) ကို Array တစ်ခုအနေနဲ့ပြန်ပေးလို့ Destructure လုပ်ပြီးလက်ခံရတယ်။

state နဲ့ setState လို့ အမည်ပေးလို့ရသလို တခြားကြိုက်တဲ့အမည်လည်းပေးလို့ရတယ်။

Note ↓ ↓

- component's name needs to be uppercase
- must be in the function/component body
- cannot call conditonally eg.if statement,loop

#### useEffect( )

useEffect( )က parameter နှစ်ခုလက်ခံတယ်။
\
first parameter က function,
second parameter က array ကို လက်ခံတယ်။

Syntax:
\
useEffect(() => {}, []);

- Render === Display

- effect => side effect => to reach the outside world [ဆိုလိုတာကcomponentထဲမှာပဲမဟုတ်ဘဲတခြားပြင်ပ external system( Eg: backend server, API request)တွေနဲ့ဆက်သွယ်ဖို့အတွက်သုံးတယ်။]

- by default it runs after every re-render [ဆိုလိုတာက componentကrenderလုပ်တိုင်းမှာ useEffect()က run တာ]

- cannot conditional

- second parameter => only run initial render

- cleanup function [ဆိုလိုတာက size ဆိုရင် resize]

- fetch Data => https://api.github.com/users

- conditional rendering

---

### useSession()

- Client Side: Yes
- Server Side: No

- to check user login state
- to obtain session information

- if a session exists, conditionally render the signin and signout links

Note; useSession() returns an object containing two values: data and status

data

- data: this can be three values: Session / undefined / null

1. Session

   in case of success, data will be Session.

2. undefined

   when the session hasn't been fetched yet, data will be undefined

3. null

   in case it failed to retrieve the session, data will be null

status

- status: enum mapping to three possible session states: "loading" | "authenticated" | "unauthenticated"

### getProviders()

The getProviders() method returns the list of providers currently configured for sign in.

It calls /api/auth/providers and returns a list of the currently configured authentication providers.

It can be useful if you are creating a dynamic custom sign in page.
