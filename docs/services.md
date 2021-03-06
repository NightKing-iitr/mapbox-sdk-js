<!-- Generated by documentation.js. Update this documentation by updating the source code. -->

### Table of Contents

- [Styles](#styles)
  - [getStyle](#getstyle)
  - [createStyle](#createstyle)
  - [updateStyle](#updatestyle)
  - [deleteStyle](#deletestyle)
  - [listStyles](#liststyles)
  - [putStyleIcon](#putstyleicon)
  - [deleteStyleIcon](#deletestyleicon)
  - [getStyleSprite](#getstylesprite)
  - [getFontGlyphRange](#getfontglyphrange)
  - [getEmbeddableHtml](#getembeddablehtml)
- [Static](#static)
  - [getStaticImage](#getstaticimage)
- [Uploads](#uploads)
  - [listUploads](#listuploads)
  - [createUploadCredentials](#createuploadcredentials)
  - [createUpload](#createupload)
  - [getUpload](#getupload)
  - [deleteUpload](#deleteupload)
- [Datasets](#datasets)
  - [listDatasets](#listdatasets)
  - [createDataset](#createdataset)
  - [getMetadata](#getmetadata)
  - [updateMetadata](#updatemetadata)
  - [deleteDataset](#deletedataset)
  - [listFeatures](#listfeatures)
  - [putFeature](#putfeature)
  - [getFeature](#getfeature)
  - [deleteFeature](#deletefeature)
- [Tilequery](#tilequery)
  - [listFeatures](#listfeatures-1)
- [Tilesets](#tilesets)
  - [listTilesets](#listtilesets)
- [Geocoding](#geocoding)
  - [forwardGeocode](#forwardgeocode)
  - [reverseGeocode](#reversegeocode)
- [Directions](#directions)
  - [getDirections](#getdirections)
- [MapMatching](#mapmatching)
  - [getMatching](#getmatching)
- [Matrix](#matrix)
  - [getMatrix](#getmatrix)
- [Optimization](#optimization)
  - [getOptimization](#getoptimization)
- [Tokens](#tokens)
  - [listTokens](#listtokens)
  - [createToken](#createtoken)
  - [createTemporaryToken](#createtemporarytoken)
  - [updateToken](#updatetoken)
  - [getToken](#gettoken)
  - [deleteToken](#deletetoken)
  - [listScopes](#listscopes)
- [Data structures](#data-structures)
  - [DirectionsWaypoint](#directionswaypoint)
  - [MapMatchingPoint](#mapmatchingpoint)
  - [MatrixPoint](#matrixpoint)
  - [OptimizationWaypoint](#optimizationwaypoint)
  - [SimpleMarkerOverlay](#simplemarkeroverlay)
  - [CustomMarkerOverlay](#custommarkeroverlay)
  - [PathOverlay](#pathoverlay)
  - [GeoJsonOverlay](#geojsonoverlay)
  - [UploadableFile](#uploadablefile)
  - [Coordinates](#coordinates)
  - [BoundingBox](#boundingbox)

## Styles

Styles API service.

Learn more about this service and its responses in
[the HTTP service documentation][108].

### getStyle

Get a style.

See the [corresponding HTTP service documentation][109].

#### Parameters

- `config` **[Object][110]** 
  - `config.styleId` **[string][111]** 
  - `config.ownerId` **[string][111]?** 

Returns **MapiRequest** 

### createStyle

Create a style.

See the [corresponding HTTP service documentation][112].

#### Parameters

- `config` **[Object][110]** 
  - `config.style` **[Object][110]** Stylesheet JSON object.
  - `config.ownerId` **[string][111]?** 

Returns **MapiRequest** 

### updateStyle

Update a style.

See the [corresponding HTTP service documentation][113].

#### Parameters

- `config` **[Object][110]** 
  - `config.styleId` **[string][111]** 
  - `config.style` **[Object][110]** Stylesheet JSON object.
  - `config.lastKnownModification` **([string][111] \| [number][114] \| [Date][115])?** Datetime of last
      known update. Passed as 'If-Unmodified-Since' HTTP header.
  - `config.ownerId` **[string][111]?** 

Returns **MapiRequest** 

### deleteStyle

Delete a style.

#### Parameters

- `config` **[Object][110]** 
  - `config.styleId` **[string][111]** 
  - `config.ownerId` **[string][111]?** 

Returns **MapiRequest** 

### listStyles

List styles in your account.

#### Parameters

- `config` **[Object][110]?** 
  - `config.start` **[string][111]?** The style ID to start at, for paginated results.
  - `config.ownerId` **[string][111]?** 

Returns **MapiRequest** 

### putStyleIcon

Add an icon to a style, or update an existing one.

#### Parameters

- `config` **[Object][110]** 
  - `config.styleId` **[string][111]** 
  - `config.iconId` **[string][111]** 
  - `config.file` **[UploadableFile][116]** An SVG file.
  - `config.ownerId` **[string][111]?** 

Returns **MapiRequest** 

### deleteStyleIcon

Remove an icon from a style.

#### Parameters

- `config` **[Object][110]** 
  - `config.styleId` **[string][111]** 
  - `config.iconId` **[string][111]** 
  - `config.ownerId` **[string][111]?** 

Returns **MapiRequest** 

### getStyleSprite

Get a style sprite's image or JSON document.

See [the corresponding HTTP service documentation][117].

#### Parameters

- `config` **[Object][110]** 
  - `config.styleId` **[string][111]** 
  - `config.format` **(`"json"` \| `"png"`)**  (optional, default `"json"`)
  - `config.highRes` **[boolean][118]?** If true, returns spritesheet with 2x
      resolution.
  - `config.ownerId` **[string][111]?** 

Returns **MapiRequest** 

### getFontGlyphRange

Get a font glyph range.

See [the corresponding HTTP service documentation][119].

#### Parameters

- `config` **[Object][110]** 
  - `config.fonts` **([string][111] \| [Array][120]&lt;[string][111]>)** An array of font names.
  - `config.start` **[number][114]** Character code of the starting glyph.
  - `config.end` **[number][114]** Character code of the last glyph,
      typically equivalent to`config.start + 255`.
  - `config.ownerId` **[string][111]?** 

Returns **MapiRequest** 

### getEmbeddableHtml

Get embeddable HTML displaying a map.

See [the corresponding HTTP service documentation][121].

#### Parameters

- `config` **[Object][110]** 
- `styleId` **[string][111]** 
- `scrollZoom` **[boolean][118]** If `false`, zooming the map by scrolling will
    be disabled. (optional, default `true`)
- `title` **[boolean][118]** If `true`, the map's title and owner is displayed
    in the upper right corner of the map. (optional, default `false`)
- `ownerId` **ownerId?** 

## Static

Static API service.

Learn more about this service and its responses in
[the HTTP service documentation][122].

### getStaticImage

Get a static map image.

**If you just want the URL for the static map image, create a request
and get it's URL with `MapiRequest#url`.** This is what prior versions of the
SDK returned.

#### Parameters

- `config` **[Object][110]** 
  - `config.ownerId` **[string][111]** The owner of the map style.
  - `config.styleId` **[string][111]** The map's style ID.
  - `config.width` **[number][114]** Width of the image in pixels, between 1 and 1280.
  - `config.height` **[number][114]** Height of the image in pixels, between 1 and 1280.
  - `config.coordinates` **([Coordinates][123] \| `"auto"`)** `[longitude, latitude]`
      for the center of image; or `'auto'` to fit the map within the bounds of
      the overlay features.
  - `config.zoom` **[number][114]** Between 0 and 20.
  - `config.bearing` **[number][114]?** Between 0 and 360.
  - `config.pitch` **[number][114]?** Between 0 and 60.
  - `config.overlays` **[Array][120]&lt;Overlay>?** Overlays should be in z-index
      order: the first in the array will be on the bottom; the last will be on
      the top. Overlays are objects that match one of the following types.-   [`SimpleMarkerOverlay`][97]
    - [`CustomMarkerOverlay`][99]
    - [`PathOverlay`][101]
    - [`GeoJsonOverlay`][103]
  - `config.highRes` **[boolean][118]**  (optional, default `false`)
  - `config.insertOverlayBeforeLayer` **[string][111]?** The ID of the style layer
      that overlays should be inserted *before*.
  - `config.attribution` **[boolean][118]** Whether there is attribution
      on the map image. (optional, default `true`)
  - `config.logo` **[boolean][118]** Whether there is a Mapbox logo
      on the map image. (optional, default `true`)

Returns **MapiRequest** 

## Uploads

Uploads API service.

Learn more about this service and its responses in
[the HTTP service documentation][124].

### listUploads

List the statuses of all recent uploads.

See the [corresponding HTTP service documentation][125].

#### Parameters

- `config` **[Object][110]?** 
  - `config.reverse` **[boolean][118]?** List uploads in chronological order, rather than reverse chronological order.

Returns **MapiRequest** 

### createUploadCredentials

Create S3 credentials.

See the [corresponding HTTP service documentation][126].

Returns **MapiRequest** 

### createUpload

Create an upload.

See the [corresponding HTTP service documentation][127].

#### Parameters

- `config` **[Object][110]** 
  - `config.mapId` **[string][111]** The map ID to create or replace in the format `username.nameoftileset`.
      Limited to 32 characters (only `-` and `_` special characters allowed; limit does not include username).
  - `config.url` **[string][111]** Either of the following:-   HTTPS URL of the S3 object provided by [`createUploadCredentials`][28]
    - The `mapbox://` URL of an existing dataset that you'd like to export to a tileset.
      This should be in the format `mapbox://datasets/{username}/{datasetId}`.
  - `config.tilesetName` **[string][111]?** Name for the tileset. Limited to 64 characters.

Returns **MapiRequest** 

### getUpload

Get an upload's status.

See the [corresponding HTTP service documentation][128].

#### Parameters

- `config` **[Object][110]** 
  - `config.uploadId` **[string][111]** 

Returns **MapiRequest** 

### deleteUpload

Delete an upload.

See the [corresponding HTTP service documentation][129].

#### Parameters

- `config` **[Object][110]** 
  - `config.uploadId` **[string][111]** 

Returns **MapiRequest** 

## Datasets

Datasets API service.

Learn more about this service and its responses in
[the HTTP service documentation][130].

### listDatasets

List datasets in your account.

See the [corresponding HTTP service documentation][131].

Returns **MapiRequest** 

### createDataset

Create a new, empty dataset.

See the [corresponding HTTP service documentation][132].

#### Parameters

- `config` **[Object][110]** 
  - `config.name` **[string][111]?** 
  - `config.description` **[string][111]?** 

Returns **MapiRequest** 

### getMetadata

Get metadata about a dataset.

See the [corresponding HTTP service documentation][133].

#### Parameters

- `config` **[Object][110]** 
  - `config.datasetId` **[string][111]** 

Returns **MapiRequest** 

### updateMetadata

Update user-defined properties of a dataset's metadata.

See the [corresponding HTTP service documentation][134].

#### Parameters

- `config` **[Object][110]** 
  - `config.datasetId` **[string][111]** 
  - `config.name` **[string][111]?** 
  - `config.description` **[string][111]?** 

Returns **MapiRequest** 

### deleteDataset

Delete a dataset, including all features it contains.

See the [corresponding HTTP service documentation][135].

#### Parameters

- `config` **[Object][110]** 
  - `config.datasetId` **[string][111]** 

Returns **MapiRequest** 

### listFeatures

List features in a dataset.

This endpoint supports pagination. Use `MapiRequest#eachPage` or manually specify
the `limit` and `start` options.

See the [corresponding HTTP service documentation][136].

#### Parameters

- `config` **[Object][110]** 
  - `config.datasetId` **[string][111]** 
  - `config.limit` **[number][114]?** Only list this number of features.
  - `config.start` **[string][111]?** The ID of the feature from which the listing should
      start.

Returns **MapiRequest** 

### putFeature

Add a feature to a dataset or update an existing one.

See the [corresponding HTTP service documentation][137].

#### Parameters

- `config` **[Object][110]** 
  - `config.datasetId` **[string][111]** 
  - `config.featureId` **[string][111]** 
  - `config.feature` **[Object][110]** Valid GeoJSON that is not a `FeatureCollection`.
      If the feature has a top-level `id` property, it must match the `featureId` you specify.

Returns **MapiRequest** 

### getFeature

Get a feature in a dataset.

See the [corresponding HTTP service documentation][138].

#### Parameters

- `config` **[Object][110]** 
  - `config.datasetId` **[string][111]** 
  - `config.featureId` **[string][111]** 

Returns **MapiRequest** 

### deleteFeature

Delete a feature in a dataset.

See the [corresponding HTTP service documentation][139].

#### Parameters

- `config` **[Object][110]** 
  - `config.datasetId` **[string][111]** 
  - `config.featureId` **[string][111]** 

Returns **MapiRequest** 

## Tilequery

Tilequery API service.

Learn more about this service and its responses in
[the HTTP service documentation][140].

### listFeatures

List features within a radius of a point on a map (or several maps).

#### Parameters

- `config` **[Object][110]** 
  - `config.mapIds` **[Array][120]&lt;[string][111]>** The maps being queried.
      If you need to composite multiple layers, provide multiple map IDs.
  - `config.coordinates` **[Coordinates][123]** The longitude and latitude to be queried.
  - `config.radius` **[number][114]** The approximate distance in meters to query for features. (optional, default `0`)
  - `config.limit` **[number][114]** The number of features to return, between 1 and 50. (optional, default `5`)
  - `config.dedupe` **[boolean][118]** Whether or not to deduplicate results. (optional, default `true`)
  - `config.geometry` **(`"polygon"` \| `"linestring"` \| `"point"`)?** Queries for a specific geometry type.
  - `config.layers` **[Array][120]&lt;[string][111]>?** IDs of vector layers to query.

Returns **MapiRequest** 

## Tilesets

Tilesets API service.

Learn more about this service and its responses in
[the HTTP service documentation][141].

### listTilesets

List a user's tilesets.

#### Parameters

- `config` **[Object][110]?** 
  - `config.ownerId` **[string][111]?** 

Returns **MapiRequest** 

## Geocoding

Geocoding API service.

Learn more about this service and its responses in
[the HTTP service documentation][142].

### forwardGeocode

Search for a place.

See the [public documentation][143].

#### Parameters

- `config` **[Object][110]** 
  - `config.query` **[string][111]** A place name.
  - `config.mode` **(`"mapbox.places"` \| `"mapbox.places-permanent"`)** Either `mapbox.places` for ephemeral geocoding, or `mapbox.places-permanent` for storing results and batch geocoding. (optional, default `"mapbox.places"`)
  - `config.countries` **[Array][120]&lt;[string][111]>?** Limits results to the specified countries.
      Each item in the array should be an [ISO 3166 alpha 2 country code][144].
  - `config.proximity` **[Coordinates][123]?** Bias local results based on a provided location.
  - `config.types` **[Array][120]&lt;(`"country"` \| `"region"` \| `"postcode"` \| `"district"` \| `"place"` \| `"locality"` \| `"neighborhood"` \| `"address"` \| `"poi"` \| `"poi.landmark"`)>?** Filter results by feature types.
  - `config.autocomplete` **[boolean][118]** Return autocomplete results or not. (optional, default `true`)
  - `config.bbox` **[BoundingBox][145]?** Limit results to a bounding box.
  - `config.limit` **[number][114]** Limit the number of results returned. (optional, default `5`)
  - `config.language` **[Array][120]&lt;[string][111]>?** Specify the language to use for response text and, for forward geocoding, query result weighting.
     Options are [IETF language tags][146] comprised of a mandatory
     [ISO 639-1 language code][147] and optionally one or more IETF subtags for country or script.

Returns **MapiRequest** 

### reverseGeocode

Search for places near coordinates.

See the [public documentation][148].

#### Parameters

- `config` **[Object][110]** 
  - `config.query` **[Coordinates][123]** Coordinates at which features will be searched.
  - `config.mode` **(`"mapbox.places"` \| `"mapbox.places-permanent"`)** Either `mapbox.places` for ephemeral geocoding, or `mapbox.places-permanent` for storing results and batch geocoding. (optional, default `"mapbox.places"`)
  - `config.countries` **[Array][120]&lt;[string][111]>?** Limits results to the specified countries.
      Each item in the array should be an [ISO 3166 alpha 2 country code][144].
  - `config.types` **[Array][120]&lt;(`"country"` \| `"region"` \| `"postcode"` \| `"district"` \| `"place"` \| `"locality"` \| `"neighborhood"` \| `"address"` \| `"poi"` \| `"poi.landmark"`)>?** Filter results by feature types.
  - `config.bbox` **[BoundingBox][145]?** Limit results to a bounding box.
  - `config.limit` **[number][114]** Limit the number of results returned. If using this option, you must provide a single item for `types`. (optional, default `1`)
  - `config.language` **[Array][120]&lt;[string][111]>?** Specify the language to use for response text and, for forward geocoding, query result weighting.
     Options are [IETF language tags][146] comprised of a mandatory
     [ISO 639-1 language code][147] and optionally one or more IETF subtags for country or script.
  - `config.reverseMode` **(`"distance"` \| `"score"`)** Set the factors that are used to sort nearby results. (optional, default `'distance'`)

Returns **MapiRequest** 

## Directions

Directions API service.

Learn more about this service and its responses in
[the HTTP service documentation][149].

### getDirections

Get directions.

Please read [the full HTTP service documentation][149]
to understand all of the available options.

#### Parameters

- `config` **[Object][110]** 
  - `config.profile` **(`"driving-traffic"` \| `"driving"` \| `"walking"` \| `"cycling"`)**  (optional, default `"driving"`)
  - `config.waypoints` **[Array][120]&lt;[DirectionsWaypoint][150]>** An ordered array of [`DirectionsWaypoint`][89] objects, between 2 and 25 (inclusive).
  - `config.alternatives` **[boolean][118]** Whether to try to return alternative routes. (optional, default `false`)
  - `config.annotations` **[Array][120]&lt;(`"duration"` \| `"distance"` \| `"speed"` \| `"congestion"`)>?** Specify additional metadata that should be returned.
  - `config.bannerInstructions` **[boolean][118]** Should be used in conjunction with `steps`. (optional, default `false`)
  - `config.continueStraight` **[boolean][118]?** Sets the allowed direction of travel when departing intermediate waypoints.
  - `config.exclude` **[string][111]?** Exclude certain road types from routing. See HTTP service documentation for options.
  - `config.geometries` **(`"geojson"` \| `"polyline"` \| `"polyline6"`)** Format of the returned geometry. (optional, default `"polyline"`)
  - `config.language` **[string][111]** Language of returned turn-by-turn text instructions.
      See options listed in [the HTTP service documentation][151]. (optional, default `"en"`)
  - `config.overview` **(`"simplified"` \| `"full"` \| `"false"`)** Type of returned overview geometry. (optional, default `"simplified"`)
  - `config.roundaboutExits` **[boolean][118]** Emit insbtructions at roundabout exits. (optional, default `false`)
  - `config.steps` **[boolean][118]** Whether to return steps and turn-by-turn instructions. (optional, default `false`)
  - `config.voiceInstructions` **[boolean][118]** Whether or not to return SSML marked-up text for voice guidance along the route. (optional, default `false`)
  - `config.voiceUnits` **(`"imperial"` \| `"metric"`)** Which type of units to return in the text for voice instructions. (optional, default `"imperial"`)

Returns **MapiRequest** 

## MapMatching

Map Matching API service.

Learn more about this service and its responses in
[the HTTP service documentation][152].

### getMatching

Snap recorded location traces to roads and paths.

#### Parameters

- `config` **[Object][110]** 
  - `config.points` **[Array][120]&lt;[MapMatchingPoint][153]>** An ordered array of [`MapMatchingPoint`][91]s, between 2 and 100 (inclusive).
  - `config.profile` **(`"driving-traffic"` \| `"driving"` \| `"walking"` \| `"cycling"`)** A directions profile ID. (optional, default `driving`)
  - `config.annotations` **[Array][120]&lt;(`"duration"` \| `"distance"` \| `"speed"`)>?** Specify additional metadata that should be returned.
  - `config.geometries` **(`"geojson"` \| `"polyline"` \| `"polyline6"`)** Format of the returned geometry. (optional, default `"polyline"`)
  - `config.language` **[string][111]** Language of returned turn-by-turn text instructions.
      See [supported languages][151]. (optional, default `"en"`)
  - `config.overview` **(`"simplified"` \| `"full"` \| `"false"`)** Type of returned overview geometry. (optional, default `"simplified"`)
  - `config.steps` **[boolean][118]** Whether to return steps and turn-by-turn instructions. (optional, default `false`)
  - `config.tidy` **[boolean][118]** Whether or not to transparently remove clusters and re-sample traces for improved map matching results. (optional, default `false`)

Returns **MapiRequest** 

## Matrix

Map Matching API service.

Learn more about this service and its responses in
[the HTTP service documentation][154].

### getMatrix

Get a duration and/or distance matrix showing travel times and distances between coordinates.

#### Parameters

- `config` **[Object][110]** 
  - `config.points` **[Array][120]&lt;[MatrixPoint][155]>** An ordered array of [`MatrixPoint`][93]s, between 2 and 100 (inclusive).
  - `config.profile` **(`"driving-traffic"` \| `"driving"` \| `"walking"` \| `"cycling"`)** A Mapbox Directions routing profile ID. (optional, default `driving`)
  - `config.sources` **(`"all"` \| [Array][120]&lt;[number][114]>)?** Use coordinates with given index as sources.
  - `config.destinations` **(`"all"` \| [Array][120]&lt;[number][114]>)?** Use coordinates with given index as destinations.
  - `config.annotations` **[Array][120]&lt;(`"distance"` \| `"duration"`)>?** Used to specify resulting matrices.

Returns **MapiRequest** 

## Optimization

Optimization API service.

Learn more about this service and its responses in
[the HTTP service documentation][156].

### getOptimization

Get a duration-optimized route.

Please read [the full HTTP service documentation][156]
to understand all of the available options.

#### Parameters

- `config` **[Object][110]** 
  - `config.profile` **(`"driving"` \| `"walking"` \| `"cycling"`)**  (optional, default `"driving"`)
  - `config.waypoints` **[Array][120]&lt;[OptimizationWaypoint][157]>** An ordered array of [`OptimizationWaypoint`][95] objects, between 2 and 12 (inclusive).
  - `config.annotations` **[Array][120]&lt;(`"duration"` \| `"distance"` \| `"speed"`)>?** Specify additional metadata that should be returned.
  - `config.destination` **(`"any"` \| `"last"`)** Returned route ends at `any` or `last` coordinate. (optional, default `"any"`)
  - `config.distributions` **\[[object][110], [object][110]]?** Array of objects, each of which includes a `pickup` and `dropoff` property. `pickup` and `dropoff` properties correspond to an index in the coordinates array.
  - `config.geometries` **(`"geojson"` \| `"polyline"` \| `"polyline6"`)** Format of the returned geometries. (optional, default `"polyline"`)
  - `config.language` **[string][111]** Language of returned turn-by-turn text instructions.
      See options listed in [the HTTP service documentation][151]. (optional, default `"en"`)
  - `config.overview` **(`"simplified"` \| `"full"` \| `"false"`)** Type of returned overview geometry. (optional, default `"simplified"`)
  - `config.roundtrip` **[boolean][118]** Specifies whether the trip should complete by returning to the first location. (optional, default `true`)
  - `config.source` **(`"any"` \| `"first"`)** To begin the route, start either from the first coordinate or let the Optimization API choose. (optional, default `"any"`)
  - `config.steps` **[boolean][118]** Whether to return steps and turn-by-turn instructions. (optional, default `false`)

Returns **MapiRequest** 

## Tokens

Tokens API service.

Learn more about this service and its responses in
[the HTTP service documentation][158].

### listTokens

List your access tokens.

See the [corresponding HTTP service documentation][159].

Returns **MapiRequest** 

### createToken

Create a new access token.

See the [corresponding HTTP service documentation][160].

#### Parameters

- `config` **[Object][110]?** 
  - `config.note` **[string][111]?** 
  - `config.scopes` **[Array][120]&lt;[string][111]>?** 
  - `config.resources` **[Array][120]&lt;[string][111]>?** 

Returns **MapiRequest** 

### createTemporaryToken

Create a new temporary access token.

See the [corresponding HTTP service documentation][161].

#### Parameters

- `config` **[Object][110]?** 
  - `config.expires` **[string][111]?** 
  - `config.scopes` **[Array][120]&lt;[string][111]>?** 

Returns **MapiRequest** 

### updateToken

Update an access token.

See the [corresponding HTTP service documentation][162].

#### Parameters

- `config` **[Object][110]** 
  - `config.tokenId` **[string][111]** 
  - `config.note` **[string][111]?** 
  - `config.scopes` **[Array][120]&lt;[string][111]>?** 
  - `config.resources` **[Array][120]&lt;[string][111]>?** 

Returns **MapiRequest** 

### getToken

Get data about the client's access token.

See the [corresponding HTTP service documentation][163].

Returns **MapiRequest** 

### deleteToken

Delete an access token.

See the [corresponding HTTP service documentation][164].

#### Parameters

- `config` **[Object][110]** 
  - `config.tokenId` **[string][111]** 

Returns **MapiRequest** 

### listScopes

List your available scopes. Each item is a metadata
object about the scope, not just the string scope.

See the [corresponding HTTP service documentation][165].

Returns **MapiRequest** 

## Data structures

Data structures used in service method configuration.

### DirectionsWaypoint

Type: [Object][110]

#### Properties

- `coordinates` **[Coordinates][123]** 
- `approach` **(`"unrestricted"` \| `"curb"`)?** Used to indicate how requested routes consider from which side of the road to approach the waypoint.
- `bearing` **\[[number][114], [number][114]]?** Used to filter the road segment the waypoint will be placed on by direction and dictates the angle of approach.
    This option should always be used in conjunction with a `radius`. The first value is an angle clockwise from true north between 0 and 360,
    and the second is the range of degrees the angle can deviate by.
- `radius` **([number][114] \| `"unlimited"`)?** Maximum distance in meters that the coordinate is allowed to move when snapped to a nearby road segment.
- `waypointName` **[string][111]?** Custom name for the waypoint used for the arrival instruction in banners and voice instructions.

### MapMatchingPoint

Type: [Object][110]

#### Properties

- `coordinates` **[Coordinates][123]** 
- `approach` **(`"unrestricted"` \| `"curb"`)?** Used to indicate how requested routes consider from which side of the road to approach a waypoint.
- `radius` **[number][114]?** A number in meters indicating the assumed precision of the used tracking device.
- `isWaypoint` **[boolean][118]?** Whether this coordinate is waypoint or not. The first and last coordinates will always be waypoints.
- `waypointName` **[string][111]?** Custom name for the waypoint used for the arrival instruction in banners and voice instructions. Will be ignored unless `isWaypoint` is `true`.
- `timestamp` **(tring | [number][114] \| [Date][115])?** Datetime corresponding to the coordinate.

### MatrixPoint

Type: [Object][110]

#### Properties

- `coordinates` **[Coordinates][123]** `[longitude, latitude]`
- `approach` **(`"unrestricted"` \| `"curb"`)?** Used to indicate how requested routes consider from which side of the road to approach the point.

### OptimizationWaypoint

Type: [Object][110]

#### Properties

- `coordinates` **[Coordinates][123]** 
- `approach` **(`"unrestricted"` \| `"curb"`)?** Used to indicate how requested routes consider from which side of the road to approach the waypoint.
- `bearing` **\[[number][114], [number][114]]?** Used to filter the road segment the waypoint will be placed on by direction and dictates the angle of approach.
    This option should always be used in conjunction with a `radius`. The first value is an angle clockwise from true north between 0 and 360,
    and the second is the range of degrees the angle can deviate by.
- `radius` **([number][114] \| `"unlimited"`)?** Maximum distance in meters that the coordinate is allowed to move when snapped to a nearby road segment.

### SimpleMarkerOverlay

A simple marker overlay.

Type: [Object][110]

#### Properties

- `marker` **[Object][110]** 
  - `marker.coordinates` **\[[number][114], [number][114]]** `[longitude, latitude]`
  - `marker.size` **(`"large"` \| `"small"`)?** 
  - `marker.label` **[string][111]?** Marker symbol. Options are an alphanumeric label `a`
      through `z`, `0` through `99`, or a valid [Maki][166]
      icon. If a letter is requested, it will be rendered in uppercase only.
  - `marker.color` **[string][111]?** A 3- or 6-digit hexadecimal color code.

### CustomMarkerOverlay

A marker overlay with a custom image.

Type: [Object][110]

#### Properties

- `marker` **[Object][110]** 
  - `marker.coordinates` **\[[number][114], [number][114]]** `[longitude, latitude]`
  - `marker.url` **[string][111]** 

### PathOverlay

A stylable line.

Type: [Object][110]

#### Properties

- `path` **[Object][110]** 
  - `path.coordinates` **[Array][120]&lt;\[[number][114], [number][114]]>** An array of coordinates
      describing the path.
  - `path.strokeWidth` **[number][114]?** 
  - `path.strokeColor` **[string][111]?** 
  - `path.strokeOpacity` **[number][114]?** Must be paired with strokeColor.
  - `path.fillColor` **[string][111]?** Must be paired with strokeColor.
  - `path.fillOpacity` **[number][114]?** Must be paired with fillColor.

### GeoJsonOverlay

GeoJSON to overlay the map.

Type: [Object][110]

#### Properties

- `geoJson` **[Object][110]** Valid GeoJSON.

### UploadableFile

In Node, files must be `ReadableStream`s or paths pointing for the file in the filesystem.

In the browser, files must be `Blob`s or `ArrayBuffer`s.

Type: ([Blob][167] \| [ArrayBuffer][168] \| [string][111] | ReadableStream)

### Coordinates

`[longitude, latitude]`

Type: [Array][120]&lt;[number][114]>

### BoundingBox

`[minLongitude, minLatitude, maxLongitude, maxLatitude]`

Type: [Array][120]&lt;[number][114]>

[1]: #styles

[2]: #getstyle

[3]: #parameters

[4]: #createstyle

[5]: #parameters-1

[6]: #updatestyle

[7]: #parameters-2

[8]: #deletestyle

[9]: #parameters-3

[10]: #liststyles

[11]: #parameters-4

[12]: #putstyleicon

[13]: #parameters-5

[14]: #deletestyleicon

[15]: #parameters-6

[16]: #getstylesprite

[17]: #parameters-7

[18]: #getfontglyphrange

[19]: #parameters-8

[20]: #getembeddablehtml

[21]: #parameters-9

[22]: #static

[23]: #getstaticimage

[24]: #parameters-10

[25]: #uploads

[26]: #listuploads

[27]: #parameters-11

[28]: #createuploadcredentials

[29]: #createupload

[30]: #parameters-12

[31]: #getupload

[32]: #parameters-13

[33]: #deleteupload

[34]: #parameters-14

[35]: #datasets

[36]: #listdatasets

[37]: #createdataset

[38]: #parameters-15

[39]: #getmetadata

[40]: #parameters-16

[41]: #updatemetadata

[42]: #parameters-17

[43]: #deletedataset

[44]: #parameters-18

[45]: #listfeatures

[46]: #parameters-19

[47]: #putfeature

[48]: #parameters-20

[49]: #getfeature

[50]: #parameters-21

[51]: #deletefeature

[52]: #parameters-22

[53]: #tilequery

[54]: #listfeatures-1

[55]: #parameters-23

[56]: #tilesets

[57]: #listtilesets

[58]: #parameters-24

[59]: #geocoding

[60]: #forwardgeocode

[61]: #parameters-25

[62]: #reversegeocode

[63]: #parameters-26

[64]: #directions

[65]: #getdirections

[66]: #parameters-27

[67]: #mapmatching

[68]: #getmatching

[69]: #parameters-28

[70]: #matrix

[71]: #getmatrix

[72]: #parameters-29

[73]: #optimization

[74]: #getoptimization

[75]: #parameters-30

[76]: #tokens

[77]: #listtokens

[78]: #createtoken

[79]: #parameters-31

[80]: #createtemporarytoken

[81]: #parameters-32

[82]: #updatetoken

[83]: #parameters-33

[84]: #gettoken

[85]: #deletetoken

[86]: #parameters-34

[87]: #listscopes

[88]: #data-structures

[89]: #directionswaypoint

[90]: #properties

[91]: #mapmatchingpoint

[92]: #properties-1

[93]: #matrixpoint

[94]: #properties-2

[95]: #optimizationwaypoint

[96]: #properties-3

[97]: #simplemarkeroverlay

[98]: #properties-4

[99]: #custommarkeroverlay

[100]: #properties-5

[101]: #pathoverlay

[102]: #properties-6

[103]: #geojsonoverlay

[104]: #properties-7

[105]: #uploadablefile

[106]: #coordinates

[107]: #boundingbox

[108]: https://www.mapbox.com/api-documentation/#styles

[109]: https://www.mapbox.com/api-documentation/#retrieve-a-style

[110]: https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Object

[111]: https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/String

[112]: https://www.mapbox.com/api-documentation/#create-a-style

[113]: https://www.mapbox.com/api-documentation/#update-a-style

[114]: https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Number

[115]: https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Date

[116]: #uploadablefile

[117]: https://www.mapbox.com/api-documentation/?language=JavaScript#retrieve-a-sprite-image-or-json

[118]: https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Boolean

[119]: https://www.mapbox.com/api-documentation/?language=JavaScript#retrieve-font-glyph-ranges

[120]: https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Array

[121]: https://www.mapbox.com/api-documentation/?language=JavaScript#embed-a-style

[122]: https://www.mapbox.com/api-documentation/#static

[123]: #coordinates

[124]: https://www.mapbox.com/api-documentation/#uploads

[125]: https://www.mapbox.com/api-documentation/#retrieve-recent-upload-statuses

[126]: https://www.mapbox.com/api-documentation/#retrieve-s3-credentials

[127]: https://www.mapbox.com/api-documentation/#create-an-upload

[128]: https://www.mapbox.com/api-documentation/#retrieve-upload-status

[129]: https://www.mapbox.com/api-documentation/#remove-an-upload

[130]: https://www.mapbox.com/api-documentation/#datasets

[131]: https://www.mapbox.com/api-documentation/#list-datasets

[132]: https://www.mapbox.com/api-documentation/#create-dataset

[133]: https://www.mapbox.com/api-documentation/#retrieve-a-dataset

[134]: https://www.mapbox.com/api-documentation/#update-a-dataset

[135]: https://www.mapbox.com/api-documentation/#delete-a-dataset

[136]: https://www.mapbox.com/api-documentation/#list-features

[137]: https://www.mapbox.com/api-documentation/#insert-or-update-a-feature

[138]: https://www.mapbox.com/api-documentation/#retrieve-a-feature

[139]: https://www.mapbox.com/api-documentation/#delete-a-feature

[140]: https://www.mapbox.com/api-documentation/#tilequery

[141]: https://www.mapbox.com/api-documentation/#tilesets

[142]: https://www.mapbox.com/api-documentation/#geocoding

[143]: https://www.mapbox.com/api-documentation/#search-for-places

[144]: https://en.wikipedia.org/wiki/ISO_3166-1_alpha-2

[145]: #boundingbox

[146]: https://en.wikipedia.org/wiki/IETF_language_tag

[147]: https://en.wikipedia.org/wiki/List_of_ISO_639-1_codes

[148]: https://www.mapbox.com/api-documentation/#retrieve-places-near-a-location

[149]: https://www.mapbox.com/api-documentation/#directions

[150]: #directionswaypoint

[151]: https://www.mapbox.com/api-documentation/#instructions-languages

[152]: https://www.mapbox.com/api-documentation/#map-matching

[153]: #mapmatchingpoint

[154]: https://www.mapbox.com/api-documentation/#matrix

[155]: #matrixpoint

[156]: https://www.mapbox.com/api-documentation/#optimization

[157]: #optimizationwaypoint

[158]: https://www.mapbox.com/api-documentation/#tokens

[159]: https://www.mapbox.com/api-documentation/#list-tokens

[160]: https://www.mapbox.com/api-documentation/#create-token

[161]: https://www.mapbox.com/api-documentation/#create-temporary-token

[162]: https://www.mapbox.com/api-documentation/#update-a-token

[163]: https://www.mapbox.com/api-documentation/#retrieve-a-token

[164]: https://www.mapbox.com/api-documentation/?language=cURL#delete-a-token

[165]: https://www.mapbox.com/api-documentation/#list-scopes

[166]: https://www.mapbox.com/maki/

[167]: https://developer.mozilla.org/docs/Web/API/Blob

[168]: https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/ArrayBuffer
