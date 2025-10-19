
## Enhancement: Show Graticule Toggle

### Overview
As part of the technical test task, a new checkbox was added to the sample JavaFX mapping application
to toggle the visibility of the **MapGraticule** (grid lines) in real time using **data binding**.

---

## Implementation Details

### 1. FXML Update 
- Added a new checkbox to the bottom sidebar:
```xml
    <CheckBox fx:id="graticuleCheckBox"
              text="Show Graticule"
              selected="true" />
```
### 2. FXML Controller
- **File affected:** `FXMLController.java`
- **Changes:**
    1. Added a new variable for the checkbox
    2. Injected the MapGraticule component to control its visibility
    3. Initialized data binding in the initialize method 
```java
@FXML
private CheckBox graticuleCheckBox;
@FXML
private MapGraticule mapGraticule;
@FXML
public void initialize() {
    // Bind the visibility of the graticule to the checkbox selection
    mapGraticule.visibleProperty().bind(graticuleCheckBox.selectedProperty());
}
```
### 3. Effect
- When the checkbox is selected → the graticule (MapGraticule) becomes visible.
- When the checkbox is unselected → the graticule is hidden.
- Changes happen instantly without the need for restarting the application.

### 4. Note
- Using data binding reduces the required code and makes UI control more flexible and easier.


