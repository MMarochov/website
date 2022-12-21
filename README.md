# Personal Website (the responsive version)
This is my personal website, made with Svelte.

## Dev notes
- All input text is in app.svelte (named slots?)
- Mouse message
- CV download / view

## Dev and Deployment

For dev:
- ```npm install```
- ```npm run dev```

To deploy on github pages, make a ```gh-pages``` branch, go to Settings > Pages > Build and Deployment and set branch to ```gh-pages /(root)```. 

Then run the following commands in the terminal:
- ```npm run build```
- ```npm run deploy```

And watch Actions do some magic!
