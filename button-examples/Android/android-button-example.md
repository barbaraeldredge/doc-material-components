# Buttons

[Buttons](https://material.io/components/buttons/) allow users to take actions, and make choices, with a single tap.

There are four types of buttons:

* [Text button](#text-button)
* [Outlined button](#outlined-button) 
* [Contained button](#contained-button)
* [Toggle button](#toggle-button)

<!-- TODO(b/1234568): Add example image here when it is available. -->

## Using buttons

Before you can implement a Material button, you need to [install the Material Components for Android library](https://github.com/material-components/material-components-android/blob/master/docs/getting-started.md).

## [Text button](https://material.io/components/buttons/#text-button)

Text buttons are typically used for less-pronounced actions, including those located in dialogs and cards. In cards, text buttons help maintain an emphasis on card content.

### Text button example

Source code API:

* MaterialButton
    * [Class description](https://developer.android.com/reference/com/google/android/material/button/MaterialButton)
    * [GitHub source](https://github.com/material-components/material-components-android/blob/master/lib/java/com/google/android/material/button/MaterialButton.java)

The following example shows a text button with purple text on a white background.

<img src="assets/android_text.png" alt="Text button example for Android with the purple text 'Text' over a white background.">

```xml
    <Button
        android:id="@+id/button3"
        style="@style/Widget.MaterialComponents.Button.TextButton"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="Text"
	...
    />
```

## [Outlined button](https://material.io/components/buttons/#outlined-button)

Outlined buttons are medium-emphasis buttons. They contain actions that are important, but aren’t the primary action in an app.

### Outlined button example

Source code API:

* MaterialButton
    * [Class description](https://developer.android.com/reference/com/google/android/material/button/MaterialButton)
    * [GitHub source](https://github.com/material-components/material-components-android/blob/master/lib/java/com/google/android/material/button/MaterialButton.java)

The following example shows an outlined button with purple text and a gray stroke.

<img src="assets/android_outlined.png" alt="Outlined button example for Android with the purple text 'Text' surrounded by a gray outline.">

```xml
    <Button
        android:id="@+id/button2"
        style="@style/Widget.MaterialComponents.Button.OutlinedButton"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="Outlined"
	...
    />
```

## [Contained button] (https://material.io/components/buttons/#contained-button)

Contained buttons are high-emphasis, distinguished by their use of elevation and fill. They contain actions that are primary to your app.

### Contained button example

Source code API:

* MaterialButton
    * [Class description](https://developer.android.com/reference/com/google/android/material/button/MaterialButton)
    * [GitHub source](https://github.com/material-components/material-components-android/blob/master/lib/java/com/google/android/material/button/MaterialButton.java)


The following example shows a contained button with white text on a purple background.

<img src="assets/android_contained.png" alt="Contained button example for Android with the white text 'Text' on a purple background.">

```xml
    <Button
        android:id="@+id/button4"
        style="@style/Widget.MaterialComponents.Button"
        android:layout_width="wrap_content"
	android:layout_height="wrap_content"
        android:text="Contained"
	...
    />

```

## [Toggle button[(https://material.io/components/buttons/#toggle-button)

Toggle buttons can be used to group related options. To emphasize groups of related toggle buttons, a group should share a common container.

There are two types of toggle buttons:
* [Toggle bar](#toggle-bar)
* [Toggle icon button](#toggle-icon-button)

### Toggle bar

The toggle bar is a group of related toggle buttons sharing a common container.

#### Toggle bar example

The following example shows a toggle bar with the following icons:
* aspect ratio
* assignment
* late assignment
* bookmark

The example allows multiple buttons to be selected. If only one option in the group should be selected and active at a time, add `app:singleSelection="true"` to `MaterialButtonToggleGroup`. This ensures that selecting one option deselects any other.

Source code APIs:

* MaterialButton
    * [Class description](https://developer.android.com/reference/com/google/android/material/button/MaterialButton)
    * [GitHub source](https://github.com/material-components/material-components-android/blob/master/lib/java/com/google/android/material/button/MaterialButton.java)

* MaterialButtonToggleGroup
    * [Class description](https://developer.android.com/reference/com/google/android/material/button/MaterialButtonToggleGroup)
    * [GitHub source](https://github.com/material-components/material-components-android/blob/master/lib/java/com/google/android/material/button/MaterialButtonToggleGroup.java)

<img src="assets/android_button_bar.png" alt="Toggle bar example for Android displaying the following icons: aspect ratio, assignment, late assignment, and bookmark.">


```xml
 <com.google.android.material.button.MaterialButtonToggleGroup
        android:id="@+id/button_group"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        app:layout_constraintTop_toTopOf="parent"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintEnd_toEndOf="parent">
        <Button
            style="?attr/materialButtonOutlinedIconStyle"
            android:id="@+id/italic_button"
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            app:icon="@drawable/ic_aspect_ratio" />
        <Button
            style="?attr/materialButtonOutlinedIconStyle"
            android:id="@+id/bold_button"
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            app:icon="@drawable/ic_assignment_ind" />
        <Button
            style="?attr/materialButtonOutlinedIconStyle"
            android:id="@+id/underline_button"
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            app:icon="@drawable/ic_assignment_late" />
        <Button
            style="?attr/materialButtonOutlinedIconStyle"
            android:id="@+id/font_color_button"
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            app:icon="@drawable/ic_bookmark_border" />
    </com.google.android.material.button.MaterialButtonToggleGroup>

```


### Toggle icon button


The toggle icon button allows you to select from a group using an icon.


#### Toggle icon button example

Source code APIs:

* [RecyclerView](https://developer.android.com/reference/androidx/recyclerview/widget/RecyclerView)
* [FrameLayout](https://developer.android.com/reference/android/widget/FrameLayout)
* [ImageView](https://developer.android.com/reference/android/widget/ImageView)
* [CheckBox](https://developer.android.com/reference/android/widget/CheckBox)


The following example shows four images arranged in a two-by-two array with a favorite icon in the upper-right corner of each image.

<img src="assets/android_toggle_button.png" alt="Android toggle icon button example showing four images in an array with a favorite icon in the upper-right corner of each image.">

This example separates out the image and checkbox (favorite icon) element into a separate layout xml file: 
[`image_grid_item_layout.xml`](toggle_demo/app/src/main/res/layout/image_grid_item_layout.xml).

```xml
<FrameLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:tools="http://schemas.android.com/tools"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    android:id="@+id/container"
    android:layout_width="match_parent"
    android:layout_height="200dp"
    android:layout_margin="2dp"
    android:foreground="?attr/selectableItemBackground">

    <ImageView
        android:id="@+id/image_view"
        android:layout_width="match_parent"
        android:layout_height="match_parent"
        android:scaleType="centerCrop"
        android:contentDescription="@string/image_content_desc"
        tools:src="@drawable/img1"/>

    <CheckBox
        android:id="@+id/favorite_check_box"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:button="@drawable/favorite_state_list_drawable"
        app:buttonTint="@android:color/white"
        android:layout_gravity="top|end"
        android:clickable="false"/>

</FrameLayout>
```

In a separate Kotlin file &ndash; [`ImageGridAdapater.kt`](toggle_demo/app/src/main/java/io/material/togglebuttons/ImageGridAdapter.kt), the `ImageGridAdapter` interates through a list of images in the `drawable` folder referenced in [`ImageItem.kt`](toggle_demo/app/src/main/java/io/material/togglebuttons/ImageItem.kt) as the `ImageView` backgrounds.

```kt
class ImageGridAdapter(
    private val listener: Listener
) : ListAdapter<ImageItem, ImageGridViewHolder>(ImageItemDiffCallback) {

    interface Listener {
        fun onItemClicked(item: ImageItem)
    }

    override fun onCreateViewHolder(parent: ViewGroup, viewType: Int): ImageGridViewHolder {
        return ImageGridViewHolder(
            LayoutInflater.from(parent.context)
                .inflate(R.layout.image_grid_item_layout, parent, false),
            listener
        )
    }

    override fun onBindViewHolder(holder: ImageGridViewHolder, position: Int) {
        holder.bind(getItem(position))
    }
}

class ImageGridViewHolder(
    view: View,
    private val listener: ImageGridAdapter.Listener
) : RecyclerView.ViewHolder(view) {
    private val container = view.findViewById<FrameLayout>(R.id.container)
    private val imageView = view.findViewById<ImageView>(R.id.image_view)
    private val favoriteView = view.findViewById<CheckBox>(R.id.favorite_check_box)
    fun bind(item: ImageItem) {
        imageView.setImageResource(item.imageRes)
        favoriteView.isChecked = item.isFavorite
        container.setOnClickListener {
            listener.onItemClicked(item)
        }
    }
}
```

In the `actvity_main.xml` file, the list of images in arranged to fit into the `RecyclerView`:

```xml
 <androidx.recyclerview.widget.RecyclerView
        android:id="@+id/image_recycler_view"
        android:layout_width="match_parent"
        android:layout_height="0dp"
        android:paddingTop="16dp"
        app:layout_constraintTop_toBottomOf="@id/button_group"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintEnd_toEndOf="parent"/>
```


