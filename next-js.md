# Next.js Coding Style Guide

### Recommended IDE: JetBrains WebStorm

Developers must take care to **NEVER** work directly in any of the branches listed above. 

They may they **NOT** manually merge their code into the branches. Instead, a pull request must be opened once a feature has been implemented within its respective branch.

## Project Organization

New pages must be under the `/pages` directory.

Files that may not be modified by a developer:

1. `/pages/_app.js or /pages/_app.tsx`
2. `/pages/_app.tsx`

```
/public/
  └── favicon.ico                   // application favourite icon file
  └── assets/        
     └── imgs/                      // contains all image files used in the application
        └── brand/                  // contains all brand specific images such as logo variations etc.
     └── svgs/                      // contains SVG files
        └── icons/                  // contains any custom icon files such as icons etc.

/src/
    └── components/        
        └── ComponentDir/
        ├── index.js                 // main component file
        ├── properties.csss          // custom SCSS classes
        └── style.modules.scss       // main SCSS
    └── containers/
        └── ContainertDir/
            ├── index.js                 // main component file
            ├── properties.scss          // custom SCSS classes
            └── styles.module.scss       // main container stylesheet
    └── constants/                       
        └── index.js                     // contains all logical constants such as REGEX etc.
    └── contexts/
        └── featureDir/
            └── featureContext.js            // context init file
            ├── feautreReducer.js            // context reducer file
            └── featureState.js              // contains context logical functions
        └── types.js                         // constant types for contexts
    └── hooks/
    └── layouts/
    └── providers/
    └── services/

/styles/                            // contains all main SCSS files
    └── index.scss                  // main stylesheet
```

**Files in the `/pages` directory may NOT contain any css imports**

**components/**

Stateless components. Shouldn’t store state. Most components in this directory will be function-based components. Stuff like buttons, inputs, labels and all presentational components goes here. This components can also accept functions as props and dispatch events, but no state should be held inside.

**containers/**

Container components can store state. Containers are built mostly from the composition of presentational components with some styles to layout them together. Containers can also store internal state and access refs to provide additional logic, but all actions should be accepted as component callbacks.

## Basic Naming Conventions:

**Variables:** camelCase

**File Naming:** camelCase

**Component Directories:** PascalCase

**Component Classes:** PascalCase

**All Other Directories:** camelCase

### Directory Naming:

All class and component directories and sub-directories must follow *camelCase* standard.

### File Naming:

All files must be named using the *camelCase* standard.

#### Files in `pages/` Directory:

All *page* file names must be SEO friendly.

**Example:**
`pages/index.js` would be the root file/ screen and its URL would be https://maqsad.io

`pages/login.js` would be the login screen and its URL would be https://maqsad.io/login

### Console Logs and Alerts:

All logs and alerts **MUST** be readible and meaningful.

**Unacceptable**

    console.log('3756', subjectsCount)
    console.log('xxxxxx', getAllBoards)

**Good**

    console.log('Subjects count: ', subjectsCount)
    console.log('getAllBoards called: : ', getAllBoards)

### Variable Naming:

All variables **must** be named using the camelCase standard.

All variables **must NOT** be shortened or abbreviated, use explanatory variables:

**Unacceptable**

    let validatenumber

**Bad**

    let valNum;
    let numVal;
    let validate;

**Good**

    let validateNumber

**Components Definition**

All components must be named using the ***PascalCase*** standard.

All components must be defined as functional components and NOT as class components.

All components must be ***default exported*** and not set as *constants.*

**Example**

    export default function Dashboard () {
        ...
    }

 All components must be modularized and defined as a directory. For example if there is a modal or dialogue to be displayed, it must be made generic and added to the src/components directory.

 All components **must** have their own directory.  The main component file should be `index.js`, main stylesheet `style.scss`. SCSS custom properties may be kept in `properties.scss`.

 For example if a pricing table needs to be displayed, it will be broken down into the following sub components:

    pricing.js      // page file in /pages directory
    PackageDetail   // sub component
    PaymentHandler  // sub component for handling payment logic

