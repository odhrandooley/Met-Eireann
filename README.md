# Met-Eireann

Main Document 
- This python notebook allows you to project any area in Ireland as a Sentinel-2 satelite image, and as 5 different land cover maps, ECOSG, ESA-CCI, CORINE, Ulmas-Walsh and S2GLC. Also, produces a barplot detailing the percentage breakdown for each land cover type for each map, as well as a barplot showing what land in one map is represented as in another map.

How to use: 
- Find the lat lon coordinates for the centre of the area that you wish to project, also identify the Sentinel-2 tile in which the area is based.
- Under 'Choose Sentinel Tile Here' adjust dirfiles to give the path of the tile that contains your desired area.
- Check that you agree with the primary translaions for each map
- in 'Input Coords Here' input the latitude in 'centre_lat', the longitude in 'centre_lon' and the extent in metres either side in 'extent' for your map.
- Run the notebook and you should get 6 plots of the area and a barplot of the breakdown of the area.
- If you find the Sentinel-2 image is cloudy, you can choose the other image for that tile by changing the sentinel2safepath function

def sentinel2safepath(path):
  """
  obtain the safe path to the sentinel-2 .SAFE dir containing image and it's metadata
  path=the city path i.e /content/drive/MyDrive/UW_map/T29/Galway
  return the sentinel-2 .SAFE dir containing image and it's metadata
  """
  safepath=[os.path.join(path,f) for f in os.listdir(path) if f.endswith('SAFE')]
  if len(safepath[0])>1:
    safepath=safepath[0]
  return(safepath)
  
  in safepath=safepath[0], change 0 to 1, or vice versa, to get the other image.
