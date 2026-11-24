# Portfolio Project Data — Rasa Nusantara - Indonesian Food Recipe

- **Category:** `desktop-mobile` (`Mobile App`)
- **Category Label:** `Mobile App`
- **Accent Color:** `amber`
- **Target Assets Folder:** `public/images/projects/rasa_nusantara_indonesian_food/`
- **Required Local Images:** `banner.webp`, `image01.webp`

## TypeScript Data (`ProjectCaseStudy`)

```typescript
{
  "id": "rasa-nusantara-indonesian-food-recipe",
  "code": "PRO-05 // APP-01",
  "title": "Rasa Nusantara - Indonesian Food Recipe",
  "category": "desktop-mobile",
  "categoryLabel": "Mobile App",
  "year": "2022",
  "status": "Completed",
  "accentColor": "amber",
  "repoUrl": "https://github.com/weztcy/Rasa-Nusantara-Indonesian-Food-Recipe",
  "license": "MIT License",
  "banner": "/images/projects/rasa_nusantara_indonesian_food/banner.webp",
  "summary": "Offline native Android recipe app showcasing 20 Indonesian dishes with Glide-optimized image loading, ingredients, and step-by-step instructions.",
  "projectDescription": "Rasa Nusantara is a native Java Android mobile application designed to deliver a fast, offline-ready catalog of 20 traditional Indonesian recipes. Built with RecyclerView, Material 3 styling, and Glide image downsampling, it provides an intuitive browse-to-detail cooking experience.",
  "architectureSummary": "MainActivity binds a static 20-item RecipeData catalog to a two-column RecyclerView via RecipeAdapter and Glide, navigating via Intent extras to DetailActivity.",
  "techStack": [
    "Java",
    "Android SDK",
    "AndroidX AppCompat",
    "Material Components",
    "RecyclerView",
    "ConstraintLayout",
    "Glide",
    "Gradle",
    "JUnit"
  ],
  "telemetryMatrix": {
    "projectType": "Native Android Mobile App",
    "targetPlatform": "Android 8.0+ (API 26 to 37)",
    "primaryDomain": "Culinary & Recipe Reference",
    "architecturePipeline": "Activity -> Adapter -> Static Data",
    "testingAndAudit": "Verified",
    "projectStatus": "Completed",
    "projectYear": "2022"
  },
  "desktopMobileProjectInfo": {
    "applicationType": "Native Android Mobile App",
    "targetPlatform": "Android",
    "developmentStatus": "Completed",
    "developmentYear": "2022",
    "applicationCategory": "Culinary & Recipe Guide"
  },
  "desktopMobileBackground": "Many recipe applications require constant internet connectivity, heavy remote API calls, and cluttered navigation that slow down kitchen workflows. Rasa Nusantara addresses this by bundling 20 curated Indonesian recipes and food photography directly inside a lightweight, distraction-free Android application.",
  "desktopMobileProblemStatements": [
    {
      "title": "Network Dependency in Kitchen Workflows",
      "description": "Web-based recipe portals fail or stall in low-connectivity kitchen environments, preventing cooks from quickly checking ingredient measurements or preparation steps.",
      "issueCode": "ISSUE_01"
    },
    {
      "title": "High Memory Footprint from Unscaled Drawables",
      "description": "Loading high-resolution local JPEG food photography directly into a scrolling RecyclerView grid with setImageResource can trigger frame drops or OutOfMemoryError crashes.",
      "issueCode": "ISSUE_02"
    },
    {
      "title": "Cluttered Multi-Step Recipe Discovery",
      "description": "Overly complex culinary apps bury core cooking metadata such as preparation duration, difficulty level, and clear numbered steps behind ads or mandatory account sign-ins.",
      "issueCode": "ISSUE_03"
    }
  ],
  "desktopMobileObjectives": [
    {
      "title": "100% Offline Recipe Accessibility",
      "description": "Package all 20 traditional Indonesian recipes, descriptions, ingredients, cooking steps, and JPEG drawables locally for instant zero-latency access without network permissions.",
      "targetTag": "TARGET_01"
    },
    {
      "title": "Smooth Two-Column Grid Rendering",
      "description": "Use RecyclerView with GridLayoutManager and Glide image downsampling (800x800 center-crop) to maintain fluid vertical scrolling across all recipe cards.",
      "targetTag": "TARGET_02"
    },
    {
      "title": "Readable Step-by-Step Detail Presentation",
      "description": "Deliver an uncluttered detail layout separating dish imagery, cooking time, difficulty badge, description, bulleted ingredients, and numbered preparation steps.",
      "targetTag": "TARGET_03"
    }
  ],
  "desktopMobileFeatures": [
    {
      "title": "20-Dish Indonesian Culinary Catalog",
      "description": "Includes 20 curated recipes such as Nasi Goreng, Rendang, Soto Ayam, Rawon, Sate Ayam, Gado-Gado, and Pempek stored in a structured RecipeData repository.",
      "badge": "OFFLINE DATA"
    },
    {
      "title": "Two-Column Material Card Grid",
      "description": "Displays each recipe inside an elevated MaterialCardView with a 1:1 ConstraintLayout image ratio, dish name, cooking time icon, and orange difficulty pill.",
      "badge": "MATERIAL 3 UI"
    },
    {
      "title": "Glide Bitmap Downsampling",
      "description": "Intercepts large local JPEG drawables in RecipeAdapter.onBindViewHolder and resizes them to 800x800 pixels with center-crop scaling to optimize RAM usage.",
      "badge": "MEMORY OPT"
    },
    {
      "title": "Structured Recipe Detail Screen",
      "description": "Formats raw ingredient lists into bulleted lines and instruction arrays into double-spaced numbered steps inside a full-viewport ScrollView.",
      "badge": "DETAIL VIEW"
    }
  ],
  "desktopMobileInterfaceShowcase": [
    {
      "imageUrl": "/images/projects/rasa_nusantara_indonesian_food/image01.webp"
    }
  ],
  "desktopMobileUserFlow": {
    "summary": "Users launch directly into a responsive two-column recipe catalog grid, scan dish thumbnails, cooking times, and difficulty badges, and tap any card to open a scrollable detail view containing the dish description, bulleted ingredients, and numbered preparation steps.",
    "steps": [
      {
        "step": "01",
        "title": "Catalog Initialization",
        "description": "MainActivity sets the activity_main layout, loads the 20 Recipe instances from RecipeData.getRecipeList(), and attaches RecipeAdapter to a 2-column GridLayoutManager.",
        "actorOrNode": "MainActivity / UI Thread"
      },
      {
        "step": "02",
        "title": "Card Binding & Thumbnail Scaling",
        "description": "RecipeAdapter binds dish title, cooking time, and difficulty badge while Glide asynchronously decodes and downsamples each JPEG drawable to 800x800 pixels.",
        "actorOrNode": "RecipeAdapter / Glide"
      },
      {
        "step": "03",
        "title": "Intent-Based Detail Navigation",
        "description": "Tapping a MaterialCardView triggers OnRecipeClickListener, packing the selected recipe_id integer into an explicit Intent to launch DetailActivity.",
        "actorOrNode": "User / Android Intent"
      },
      {
        "step": "04",
        "title": "Recipe Formatting & Reading",
        "description": "DetailActivity validates recipe_id, resolves the matching Recipe record, formats bulleted ingredients and numbered steps, and renders them in a ScrollView.",
        "actorOrNode": "DetailActivity / UI Thread"
      }
    ]
  },
  "desktopMobileArchitecture": {
    "summary": "The application follows a lightweight native Android Activity-Adapter-Data architecture. MainActivity binds an in-memory RecipeData collection to a two-column RecyclerView via RecipeAdapter with Glide downsampling, while Intent extras pass selected recipe IDs to DetailActivity.",
    "layers": [
      {
        "name": "Presentation & Activity Layer",
        "role": "Manages screen lifecycle, XML view binding, RecyclerView grid setup, and Intent navigation between catalog and detail views.",
        "tech": "Android SDK & AppCompat",
        "components": ["MainActivity", "DetailActivity", "Material 3 Theme"]
      },
      {
        "name": "Adapter & Media Rendering Layer",
        "role": "Maps Recipe models to MaterialCardView items and performs memory-safe image downsampling via Glide.",
        "tech": "RecyclerView & Glide",
        "components": ["RecipeAdapter", "RecipeViewHolder", "OnRecipeClickListener"]
      },
      {
        "name": "Domain Model & Static Data Layer",
        "role": "Defines the Recipe entity schema and provides the bundled 20-dish catalog backed by local JPEG drawable resources.",
        "tech": "Java & Android Resources",
        "components": ["Recipe", "RecipeData", "res/drawable JPEG Assets"]
      }
    ]
  },
  "desktopMobileDataManagement": {
    "storageType": "In-Memory Static Java Dataset & Bundled Drawable Resources",
    "stateEngine": "Stateless Activity & Explicit Intent Extra Passing",
    "offlineSyncStrategy": "Fully Self-Contained Offline Bundle Requiring Zero Network Connectivity",
    "cachingMechanism": "Glide Memory & Resource Bitmap Caching with 800x800 Downsampling"
  },
  "desktopMobilePlatformImplementation": [
    {
      "title": "Manifest & Launcher Security Configuration",
      "description": "Declares MainActivity as exported with MAIN/LAUNCHER intent filters while keeping DetailActivity internal (exported=false) and enforcing zero dangerous OS permissions.",
      "badge": "ANDROID MANIFEST"
    },
    {
      "title": "Material 3 DayNight & Edge-to-Edge Bar Styling",
      "description": "Configures Theme.Material3.DayNight.NoActionBar with matching warm cream status and navigation bar colors (#FFF8F3) and light system bar icon flags.",
      "badge": "SYSTEM UI"
    },
    {
      "title": "Gradle Kotlin DSL & Version Catalog Build",
      "description": "Centralizes dependency coordinates in gradle/libs.versions.toml with Gradle configuration caching enabled and Java 11 bytecode compatibility for API 26–37.",
      "badge": "GRADLE BUILD"
    }
  ],
  "desktopMobileTechSpecs": {
    "programmingLanguage": "Java",
    "framework": "Android SDK",
    "localStorage": "Static In-Memory Dataset"
  },
  "desktopMobilePlatformSpecs": {
    "targetPlatform": "Android Mobile Devices",
    "packageFormat": "Android APK Package",
    "targetArchitecture": "Universal Android ABI",
    "buildFootprint": "21.3 MB Debug APK"
  }
}
```
