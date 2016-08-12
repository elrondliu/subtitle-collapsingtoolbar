# SubtitleCollapsingToolbarLayout
this layout is a CollapsingToolbarLayout with subtitle support. Ever wondered how WhatsApp did with their contacts profile activity? this layout is mimicking that behaviour.

<img src="https://dl.dropbox.com/s/tc7y8zspfbxdjrl/collapsing%20toolbar%20layout.gif" height="550" width="300"/>

## Usage

`git clone https://github.com/ahmadmuzakki29/subtitle-collapsingtoolbar`

then on **Android Studio** you can import the module with **File**->**New**->**Import Module** and choose module **:subtitlecollapsingtoolbar** inside downloaded folder

**Available new attributes**:
```
app:subtitle="string"
app:collapsedSubtitleAppearance="reference"
app:expandedSubtitleAppearance="reference"
```


### Quick snippet : 
```xml
<?xml version="1.0" encoding="utf-8"?>
<android.support.design.widget.CoordinatorLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:fitsSystemWindows="true">

    <android.support.design.widget.AppBarLayout
        android:layout_width="match_parent"
        android:layout_height="192dp"
        android:background="?attr/colorPrimary"
        android:fitsSystemWindows="true">

        <com.muzakki.ahmad.widget.CollapsingToolbarLayout
            android:id="@+id/collapsing"
            android:layout_width="match_parent"
            android:layout_height="match_parent"
            app:layout_scrollFlags="scroll|exitUntilCollapsed"
            app:contentScrim="@color/colorAccent"
            app:collapsedTitleTextAppearance="@style/title.collapsed"
            app:expandedTitleTextAppearance="@style/title.expanded"
            app:collapsedSubtitleAppearance="@style/subtitle"
            app:expandedSubtitleAppearance="@style/subtitle"
            app:title="Pendet"
            app:subtitle="Bali, Indonesia"
            android:fitsSystemWindows="true"
            >
            <ImageView
                android:layout_height="match_parent"
                android:layout_width="match_parent"
                android:src="@drawable/pendet_dance"
                android:adjustViewBounds="true"
                android:scaleType="centerCrop"
                app:layout_collapseMode="parallax"
                />
            <android.support.v7.widget.Toolbar
                android:id="@+id/toolbar"
                android:layout_width="match_parent"
                android:layout_height="?attr/actionBarSize"
                app:layout_collapseMode="pin"/>

        </com.muzakki.ahmad.widget.CollapsingToolbarLayout>

    </android.support.design.widget.AppBarLayout>

    <android.support.v4.widget.NestedScrollView
        android:layout_width="match_parent"
        android:layout_height="match_parent"
        app:layout_behavior="@string/appbar_scrolling_view_behavior">
        <TextView
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:layout_marginLeft="@dimen/activity_horizontal_margin"
            android:layout_marginRight="@dimen/activity_horizontal_margin"
            android:layout_marginTop="@dimen/activity_vertical_margin"
            android:layout_marginBottom="@dimen/activity_vertical_margin"
            android:text="Pendet is a traditional dance from Bali, Indonesia, in which offerings are made to purify the temple or theater as a prelude to ceremonies or other dances. Pendet is typically performed by young girls, carrying bowls of flower petals, handfuls of which are cast into the air at various times in the dance. Pendet can be thought of as a dance of greeting, to welcome the audience and invite spirits to enjoy a performance." />
    </android.support.v4.widget.NestedScrollView>

</android.support.design.widget.CoordinatorLayout>
```