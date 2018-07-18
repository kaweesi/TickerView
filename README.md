# TickerView

What is TickerView?
===============
TickerView is a simple Android UI component for displaying horizontally scrolling Views placed inside this TickerView. For reference you may see how MoneyControl Tablet (https://play.google.com/store/apps/details?id=com.moneycontrol, shows stock price in scrolling view at the bottom of screen) and Phone app shows the Stock prices. The TickerView scrolls child views with smooth animation.

Getting started

---------------

Add the ticker dependency to your `build.gradle`.
```groovy
implementation 'com.vinay.ticker.lib:tickerview:0.1-alpha'
```

Usage
-----

Define the `TickerView` in XML:

```xml

<com.vinay.ticker.lib.TickerView
        android:id="@+id/tickerView"
        android:layout_width="match_parent"
        android:layout_height="wrap_content" />
```

Then in java code, add the views to the TickerView:

```java

// Get the TickerView object
final TickerView tickerView = findViewById(R.id.tickerView);

// Add multiple views to be shown in the ticker
for (int index = 0; index < 50; index++) {
	// childViews
        TextView tv = new TextView(this);
        tv.setLayoutParams(new LinearLayout.LayoutParams(FrameLayout.LayoutParams.WRAP_CONTENT, FrameLayout.LayoutParams.WRAP_CONTENT));
        tv.setText(String.valueOf(index + 1));
        tv.setBackgroundColor(ContextCompat.getColor(this, android.R.color.white));
        tv.setTextColor(ContextCompat.getColor(this, android.R.color.black));
        tv.setTextSize(TypedValue.COMPLEX_UNIT_SP, 22);
        tv.setPadding(10, 5, 10, 5);
        
	tickerView.addChildView(tv);
}

// Call the showTickers() to show them on the screen
tickerView.showTickers();

```


