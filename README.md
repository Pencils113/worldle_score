# Worldle Scorer

## Links

Worldle: https://worldle.teuteuf.fr/

Popularity data from: https://www.jetpunk.com/quizzes/how-many-countries-can-you-name

Shapefiles from: https://hub.arcgis.com/datasets/esri::world-countries-generalized/explore

Hausdorff Distance: https://en.wikipedia.org/wiki/Hausdorff_distance#:~:text=The%20Hausdorff%20distance%20is%20the,point%20in%20the%20other%20set

## Score components

- Distance score
  - max(1 - (get_min_distance(map, c1, c2) / 11110), 0)
- Shape similarity score
  - get_shape_similarity(map, c1, c2)
- Name Similarity Score
  - name_similarity(c1, c2)
- Size Similarity Score
  - get_size_similarity(map, c1, c2)
- Popularity Similarity Score (for c1 and c2)
  - get_popularity(popularity_data, c1)

### Final Calculated Score

max((1 - 0.1 * NUM_GUESSES), 0) + (np.mean(np.array(scores))) / 10
