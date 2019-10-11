[Go to step 3](https://github.com/seattleacademy/faceCam/tree/step3)
# faceCam
A face recognition tutorial using the browser
## Step 4  Load models and recognize faces
1.  In the script tag at the bottom of index.html, add the loadModels function to load weights. 
```javascript
    async function loadModels() {
        //let weightsURI = "weights";
        let weightsURI = "https://seattleacademy.github.io/faceRoster/weights";
        await faceapi.nets.ssdMobilenetv1.load(weightsURI);
    }
```
2.  Add also to the scripts to display in the console faces detected.
 ```javascript  
    async function updateResults() {
        results = await faceapi.detectAllFaces("myImg");
        console.log(results);
    } 
```
3.  Just before the end of the script tag, call the function loadModels followed by updateResults after the models have been loaded.
```javascript
    loadModels().then(updateResults);
```
4. Remove any other calls to console. 
5. Check in the debugger that the software is detecting all face in the sample and uploaded images. In particular, the score should give a value that signifies the likelyhood of matching a face.

[Go to step 5](https://github.com/seattleacademy/faceCam/tree/step5)
