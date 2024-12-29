### Files 📁
 
1. **`COCO_val_annos.json`**: Annotations for vehicle damage categories.
2. **`COCO_mul_val_annos.json`**: Annotations for vehicle parts categories.
3. **`img`**: Folder containing images referenced in the JSON files.
4. **`coco.zip`**: Compressed version of the dataset.
5. **`script.py`**: Python script for loading and visualizing dataset annotations.

## Prerequisites ⬇️

Ensure the following Python libraries are installed:

- `matplotlib`
- `pycocotools`
- `numpy`
- `scikit-image`
- `seaborn`
- `Pillow (PIL)`
- `tensorboard`

Install them using:

```bash
pip install matplotlib pycocotools numpy scikit-image seaborn pillow tensorboard
```
👍

## Setup Instructions

1. **Unzip the Dataset**:
   Extract `coco.zip` to ensure the `val/` and `img/` directories are available.

   ```bash
   unzip coco.zip
   ```

2. **Run the Script**:
   Execute `script.py` to load annotations, display images, and visualize annotations.

   ```bash
   python script.py
   ```

## Code Overview 👓

The provided script performs the following tasks:

### 1. **Library Imports**

Imports required libraries for mathematical operations, image processing, and visualization:

- `pycocotools`: Handle COCO dataset annotations.
- `matplotlib` and `seaborn`: Visualization.
- `numpy` and `Pillow`: Array operations and image manipulation.

### 2. **Dataset Loading**

- **Damage Annotations**: Loaded using `COCO_val_annos.json`.
- **Parts Annotations**: Loaded using `COCO_mul_val_annos.json`.

### 3. **Categories and Supercategories**

Extracts and prints:

- Categories (e.g., specific damages like dents or scratches).
- Supercategories (e.g., broader classifications).

### 4. **Random Image Selection**

Selects a random image from the dataset for visualization.

```python
random_img_id = random.choice(imgIds)
```

### 5. **Image Display**

Displays the selected image using `skimage.io` and `matplotlib`.

```python
plt.axis('off')
plt.imshow(I)
plt.show()
```

### 6. **Annotations Visualization**

- **Damages**: Visualized using bounding boxes around identified damages.
- **Parts**: Visualized with annotations overlaid on the image.

```python
coco.showAnns(anns, draw_bbox=True)
mul_coco.showAnns(mul_anns, draw_bbox=True)
```

### 7. **Parts Identification**

Maps part category IDs to names and lists the parts identified in the image.

```python
parts = [category_map[region['category_id']] for region in mul_anns]
print("Parts are:", parts)
```

## Example Output

Upon running the script, the following outputs will be generated:

1. **Categories and Supercategories**:
   ```plaintext
   COCO categories for damages:
   category1, category2, ...

   COCO supercategories for damages:
   supercategory1, supercategory2, ...
   ```

2. **Random Image Selection**:
   Displays a randomly selected image from the dataset.

3. **Annotations Visualization**:
   Overlays annotations for damages and parts on the image.


