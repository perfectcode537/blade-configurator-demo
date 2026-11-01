BLADE STUDIO - 3D blade configurator demo
==========================================

Files: index.html (viewer) + model.js (blade data from the Flared Fusion 360 model).
Three.js r160 from CDN, no build step.

NOTE: model.js is loaded as a module, so the page must be served over http
(GitHub Pages, Netlify, or "python -m http.server" locally). Double-clicking
index.html from disk will not load the model.

PUT IT ONLINE
- Netlify: https://app.netlify.com/drop and drag this "demo" folder on the page
- or GitHub Pages: Settings > Pages > Deploy from branch > main / root

WHAT IS IN THE DEMO
- The client's real Flared blade: exact outline and handle halves from Flared.obj
- Blade rebuilt as real plies: face veneer, inner plies, core, optional composite
  (carbon / arylate carbon / zylon carbon), visible on the edge and in the exploded view
- Wood from real scanned veneers (colour + normal map, textures/ folder), colour matched
  to the real product photos: palisander, ebony, walnut, limba, koto, hinoki, ayous, kiri,
  wenge, ash. Scans: Poly Haven, CC0 licence (free for commercial use).
  New wood = add a scan or photo of the real veneer with tools/prep_textures.py
- Palisander front and back are made from the original full-size Palis product photos
  (tools/prep_photo_wood.py maps the photo onto the CAD outline), 4096 px, real pores and fibres;
  normal maps from the photo pores (tools/photo_normal.py)
- Handle wood taken from the real Palis handle photo (tools/prep_handle_wood.py), matte hand-sanded
- Sanded round edge on the face veneers, matte end-grain ply edges
- Natural / satin / gloss finish (clearcoat)
- Handle wood + handle print (model name + class) on a glossy black inlay plate
- Domed country badge with brass bezel on the back of the handle
- Laser-engraved serial number on the face and on the ply edge of the handle
- White enamel medallion with black rings on the handle butt (silver / gold rim / none)
- Rubber preview, live price and estimated weight (wood densities x real volume)
- Save HD render: PNG up to 3600 px on white background, like shop product photos
- Add to cart summary (in the real shop this goes to the WooCommerce cart)

SHAREABLE DESIGN LINKS
index.html?outer=ebony&handleWood=wenge&finish=gloss&printText=NOVA&printClass=ALL%2B&printColor=gold#hero
Views after #: front, hero, back, plies, handle, badge, butt, serial, side, explode

REBUILD model.js FROM A NEW CAD EXPORT
python ../tools/prep_model.py ../files/Flared.obj model.js
