# Flux Full Stack Dev Assessment
This is a [Next.js](https://nextjs.org/) project bootstrapped with [`create-next-app`](https://github.com/vercel/next.js/tree/canary/packages/create-next-app).

## Objective: 

In this assessment, you will be making a full stack web app that does the following:
- Protected admin page (simple login)
- Admin page should have a list of cars table with 3 dots menu to delete a car
- Admin page should have a form to add/update a car (same view is fine)
- A public page that shows a list of cars in a 3x3 grid
- Pricing of the car is a matrix

Let's dive in:

## Tech Stack
Clone this repo and run `pnpm install` to install dependencies. Here's what you'll need to get started:

### Frontend
- Next.js
- Tailwind CSS
- Typescript

### Backend
- Next.js api routes
- Typescript

### Database
- Prisma for the database
You can use a free instance of MongoDB from Mongo Atlas or local MongoDB ReplicaSet. We should be able to use an environment variable to set the database URL from our side to connect to our test database. [https://prisma.io/](https://prisma.io/)

### Package Manager
Use `pnpm` as the package manager for this project. [https://pnpm.io/](https://pnpm.io/)

## API
Make api routes to handle the following:
- GET /api/cars - get all cars
- GET /api/cars/:id - get a car by id
- POST /api/cars - create a car
- PUT /api/cars/:id - update a car by id
- DELETE /api/cars/:id - delete a car by id

Remember to validate the request body using your validation tool of choice.

## Admin Login Page
Make a protected admin page that has a login form. The login form should have a username and password field. When the user submits the form, the page should check if the username and password are correct. If they are, the user should be redirected to the admin page. If not, the user should be redirected to the login page.

## Admin Car Page
- Make an admin page that has a list of cars. 
- The list of cars should be displayed in a table with 3 dots menu to delete a car.
- One page to create/update a car.

The fields for the cars should be:
- Brand
- Model
- Year
- Image (can be just a link to an image, if you prefer)
- Pricing (we elaborate below)

## Pricing Matrix (Admin Car Page)
We want to make a pricing table for different plans (Month to month, 12/24/36 months) and different mileage packages (lite, standard, unlimited).

When we edit any number on the table, it should be updated as is, **except** for the "lite" column; when you edit any number in the light column, the row should be updated automatically.

- The table should have an edit button to make it editable.
- The table should have a reset button to set all pricing to 0.
- When the column "lite" is edited, the row should be updated automatically with x2 and x3 multipliers for standard and unlimited, respectively.

### Example editing the table:

| | lite | standard | unlimited |
|----------|------|----------|-----------|
| 36months | 1000 | 1200 | 1600 |
| 24months | 1200 | 1400 | 1800 |

If we change 36months standard to **1500**,  the table should look like this:
| | lite | standard | unlimited |
|----------|------|----------|-----------|
| 36months | 1000 | 1500 | 1600 |
| 24months | 1200 | 1400 | 1800 |

If we change 24months lite, the next columns will be multiplied by **x2** and **x3** respectively:
| | lite | standard | unlimited |
|----------|------|----------|-----------|
| 36months | 1000 | 1500 | 1600 |
| 24months | 1200 | 2400 | 3600 |

If we change 24months unlimited to **5000**, the the table, finally, becomes:
| | lite | standard | unlimited |
|----------|------|----------|-----------|
| 36months | 1000 | 1500 | 1600 |
| 24months | 1200 | 2400 | 5000 |

## Public Page
- Make a public page that fetches the list of cars from the admin page and shows a list of cars in a 3x3 grid with pagination.
- Page should have a search bar, the search should filter based on the brand and model.

## Considerations
The projects should be small enough, it is just a a quick way to demonstrate various abilities. Use the styling that you want, we won't judge based on how the design looks like. Tailwind should simplify the styling.

Keep in mind, this is going to run on Vercel, a serverless platform.

Testing is not a requirement, but it is a plus if you have time.

## Submission
Clone this repo into your own account and give us access to the repo.
We will clone it, change env variables and deploy it to Vercel.