!!! info
    If you want some helping information for any of the modes of the editing menu from inside the application press the i-button at the top of the respective mode menu. 
    
<video controls>
    <source src="../images_compressed/help_in_modes_webm.webm" type="video/webm">
</video>

*Figure 3: open help in one of the modes of the editing menu (here: Import/Export)*

# Editing menu

## Import/Export

With this menu you can import one or more of the following:

* a model of a cuneiform tablet (.ply file)
* annotations (.json file)
* a transliteration (.json file)

Models and annotations can be imported either from a local file on your computer or from a URL.

!!! info "Example of a URL to a model of a cuneiform tablet"
    ```
    https://heidicon.ub.uni-heidelberg.de/eas/partitions/1/0/577000/577526/97a78512f61fae4dbdf80c43e7725822a3a23308/application/x-ply/HS_1174_HeiCuBeDa_GigaMesh.ply
    ```
    
Pressing **Reset** on the lower left side of the screen resets all cuneiform tablets and annotations that were loaded in this use of the **Import/Export** menu.
Pressing **Done** on the lower left side of the screen confirms the imports you made and leads you back to the main menu. 

In the following the available options are explained in more detail:

**Load new model (from local file)**: Loads a new cuneiform tablet from a ply-file located on your computer.

**Load new model (from URL)**: Loads a new cuneiform tablet from a ply-file accessible through a URL (e.g. from example above).

**Load new annotations (local file)**: Loads new annotations from a json-file located on your computer. It's important that the json-file stores every annotation as a key-value pair and that the value contains a key-value pair with the key 'body' and a key-value pair with the key 'target'. The latter must contain another key-value pair with the key 'selector' which contains in its value at least a key-value pair with the key 'value' and a wktstring (polygon or multilinestring) as its value.

!!! info "Example of a correctly formated .json file"
    ```json
    {
        "#010a9fdd-d84f-435b-9736-9c1f9489aeb8": {
            "type": "Annotation",
            "body": [],
            "target": {
                "selector": {
                    "type": "WKTSelector",
                    "value": "POLYGON Z((7.353779867021871 22.229301635363633 0.0,13.788443237346897 26.88200530685541 0.0,7.353779867021871 26.88200530685541 0.0,7.353779867021871 22.229301635363633 -5.37910795211792,13.788443237346897 22.229301635363633 -5.37910795211792,13.788443237346897 22.229301635363633 0.0,13.788443237346897 26.88200530685541 -5.37910795211792,7.353779867021871 26.88200530685541 -5.37910795211792))"
                }
            }
        }
    }
    ```

**Load new annotations (URL)**: Loads new annotations from a json-file accessible through a URL. The json-file must meet all criteria given in the previous paragraph.

**Load new annotations with corresponding model (local file)**: Loads new annotations from a json-file located on your computer and the cuneiform tablet behind the URL given in the 'target' key-value pair of the first annotation. The json-file must meet all criteria given above. Furthermore it must contain the key-value pair with the key 'source' in its 'target' key-value pair. The respective value must be a URL pointing to a ply-file.

**Load new annotations with corresponding model (URL)**: Loads new annotations from a json-file accessible through a URL and the cuneiform tablet behind the URL given in the 'target' key-value pair of the first annotation. The json-file must meet all criteria given in the previous paragraph.

!!! info "Example of a correctly formated .json file with 'source'"
    ```json
    {
        "#010a9fdd-d84f-435b-9736-9c1f9489aeb8": {
            "type": "Annotation",
            "body": [],
            "target": {
                "source": "https://heidicon.ub.uni-heidelberg.de/eas/partitions/1/0/577000/577526/97a78512f61fae4dbdf80c43e7725822a3a23308/application/x-ply/HS_1174_HeiCuBeDa_GigaMesh.ply",
                "selector": {
                    "type": "WKTSelector",
                    "value": "POLYGON Z((7.353779867021871 22.229301635363633 0.0,13.788443237346897 26.88200530685541 0.0,7.353779867021871 26.88200530685541 0.0,7.353779867021871 22.229301635363633 -5.37910795211792,13.788443237346897 22.229301635363633 -5.37910795211792,13.788443237346897 22.229301635363633 0.0,13.788443237346897 26.88200530685541 -5.37910795211792,7.353779867021871 26.88200530685541 -5.37910795211792))"
                }
            }
        }
    }
    ```

**Load new transliteration**: Loads a json-file containing a transliteration located on your computer. The json-file must be composed of one key-value pair, where the value contains the transliteration content. New lines must be broken up through \n.

!!! info "Example of a correctly formated tranliteration .json file"
    ```json
    {"HS_1174": "@tablet\n@obverse\n1. 3(u) 3(disz) gurusz szu dim2-ma\n2. da-ak-ru-um e2-a ib2-dab5\n 3. ugula szesz-da-da\n4. 9(disz) gurusz szu dim2-ma\n@reverse\n1. ugula lu2-ga-a\n2. nu-banda3 ku3-sa6-ga\n3. e2-gal ensi2-ka\n4. sza3 tum-al!(TA)\n6. iti du6-ku3 u4 9(disz)"}
    ```

**Export annotations**: Shows a link to export the annotations which are currently displayed on the screen in a json-file. Clicking on the link downloads the json-file to your local computer.

<video controls>
  <source src="../images_compressed/import_export_webm.webm" type="video/webm">
</video>

*Figure 3: exporting annotations, importing a model (URL), importing transliterations and importing annotations (local file) on the import/export menu*

## Create new annotation (box)

To create an annotation in form of a box you first have to set the initial position of the box. For that use the mouse and click on a point on the cuneiform tablet.

The content of the annotations can be entered on the left side.

The position and size of the annotation can be changed with the GUI on the left side. To see it scroll down on the editing menu. 
Alternatively you can change the position of the box by dragging it with the mouse. 

The rotation of the box can be changed with keyboard shortcuts (the same as for rotating the model, s. [here](./getting_started.md/#rotating-the-model)). 

**Reset** deletes your created annotation and takes you back to the main menu.\
**Done** saves your created annotation and takes you back to the main menu.

<video controls>
  <source src="../images_compressed/create_box_webm.webm" type="video/webm">
</video>

*Figure 4: creating annotations as boxes*


## Create new annotation (polygon)

To create an annotation in form of a polygon start by clicking on a point on the cuneiform tablet to determine the start point of the polygon. A black dot appears. Everytime you click on a new point on the tablet the shortest line between the previous and the new point on the surface of the tablet is computed.

!!! info
    Depending on your hardware and the length of the line computation may take a while. While the line is computed nothing happens on the main screen.

Close the polygon by clicking on the starting point again (a black dot appears). Only then the form can be changed.

If you don't close the polygon manually, you will be asked if you want it to be closed automatically when pressing **Done**.

To change the form click on a point on the line (that point gets highlighted) and then click on the point on the tablet this point shall be moved to. The lines between the moved point and the endpoints of the line(s) are then redrawn.

Actions can be undone by pressing crtl+z on your keyboard.

**Reset** deletes your created annotation and takes you back to the main menu.\
**Done** saves your created annotation and takes you back to the main menu.

<video controls>
  <source src="../images_compressed/create_polygon_webm.webm" type="video/webm">
</video>

*Figure 5: creating annotations as polygons*

## Edit annotation content

To change the content of an annotation enter new inputs into the form on the editing menu. Current values are displayed as placeholders. To enter custom tags write the name of the tag into the textfield at the bottom of the form an press enter.

Inputs can be deleted by clicking on the bin-icon. Custom tags can be deleted by clicking on the tag and then on the bin-icon appearing next to the tag.

**Reset** deletes all newly entered content and takes you back to the main menu.\
**Done** confirms all newly entered content and takes you back to the main menu.

<video controls>
  <source src="../images_compressed/edit_content_webm.webm" type="video/webm">
</video>

*Figure 6: editing the content of a box annotation*

## Edit annotation form

**Box annotations**:

The position and size of the box can be changed with the GUI on the left side. 
Alternatively you can change the position of the box by dragging it with the mouse. 

The rotation of the box can be changed with keyboard shortcuts (the same as for rotating the model, s. [here](./getting_started.md/#rotating-the-model)). 

Pressing **Delete annotation** will delete the whole annotation including any content. It can be undone by pressing **Reset**.

**Reset** resets all form manipulations (except rotation) and takes you back to the main menu.\
**Done** confirms all form manipulations and takes you back to the main menu.

<video controls>
  <source src="../images_compressed/edit_form_box_webm.webm" type="video/webm">
</video>

*Figure 6: editing the form of a box annotation*

**Polygon annotations**:

The form of the line can by changed by clicking on a point on the line (that point gets highlighted) and then click on the point on the tablet this point shall be moved to. The lines between the moved point and the endpoints of the line(s) are then redrawn.

Pressing **Delete annotation** will delete the whole annotation including any content. It can be undone by pressing **Reset**.

**Reset** resets all form manipulations and takes you back to the main menu.\
**Done** confirms all form manipulations and takes you back to the main menu.

<video controls>
  <source src="../images_compressed/edit_form_polygon_webm.webm" type="video/webm">
</video>

*Figure 7: editing the form of a polygon annotation*