# Flix

Flix is an app that allows users to browse movies from the [The Movie Database API](http://docs.themoviedb.apiary.io/#).

📝 `NOTE - PASTE PART 2 SNIPPET HERE:` Paste the README template for part 2 of this assignment here at the top. This will show a history of your development process, which users stories you completed and how your app looked and functioned at each step.

## Network Request Snippet

      let url = URL(string: "https://api.themoviedb.org/3/movie/now_playing?api_key=a07e22bc18f5cb106bfe4cc1f83ad8ed")!
      let request = URLRequest(url: url, cachePolicy: .reloadIgnoringLocalCacheData, timeoutInterval: 10)
      let session = URLSession(configuration: .default, delegate: nil, delegateQueue: OperationQueue.main)
      let task = session.dataTask(with: request) { (data, response, error) in
         // This will run when the network request returns
         if let error = error {
            print(error.localizedDescription)
         } else if let data = data {
            let dataDictionary = try! JSONSerialization.jsonObject(with: data, options: []) as! [String: Any]

            // TODO: Get the array of movies
            // TODO: Store the movies in a property to use elsewhere
            // TODO: Reload your table view data

         }
      }
      task.resume()

---

## Flix Part 1

### User Stories

#### REQUIRED (10pts)
- [x] (2pts) User sees an app icon on the home screen and a styled launch screen.
- [x] (5pts) User can view and scroll through a list of movies now playing in theaters.
- [x] (3pts) User can view the movie poster image for each movie.

#### BONUS
- [ ] (2pt) User can view the app on various device sizes and orientations.
- [ ] (1pt) Run your app on a real device.

### Notes
Describe any challenges encountered while building the app.

#### Problem: 
error message “ SWIFT_VERSION ‘5.1’ is unsupported, supported versions are: 3.0, 4.0, 4.2. (in target ‘Alamofire’) ”.

#### Solution: 
First Google, but found no correct way to deal with it. Then checked Slack's history to see whether other classmates have same issues, but turned out nothing. Finally, solved by Tim's solution in updating my Xcode, which also requires me to update MacBook's software, which took me nearly one hour.

## Flix Part 2

### User Stories

#### REQUIRED (10pts)
- [x] (5pts) User can tap a cell to see more details about a particular movie.
- [x] (5pts) User can tap a tab bar button to view a grid layout of Movie Posters using a CollectionView.

#### BONUS
- [ ] (2pts) User can tap a poster in the collection view to see a detail screen of that movie.
- [ ] (2pts) In the detail view, when the user taps the poster, a new screen is presented modally where they can view the trailer.

## Video Walkthrough 

Here's a walkthrough of implemented user stories:

<img src='http://g.recordit.co/bZZi4HmhzW.gif' title='Video Walkthrough' width='' alt='Video Walkthrough' />

GIF created with [Recordit](https://recordit.co/).

### Notes
Describe any challenges encountered while building the app.

#### When I was working on the project, I found after I clicked the bar tab item "Superhero", movie posters showed in small size and 6 in a row. Then I found one of the classmates also faced the same problem in Slack. Later, I figured it out by changing the Estimate Size in the Collection View as 'None'. And the problem solved.
