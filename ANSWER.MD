# My Answers

## 1. My GitHub link
https://github.com/gianlawrencelauro-lang/flutter_basics_lab.git

## 2. The 3 build() lines from Activity 2
build() called: 4 glasses
build() called: 5 glasses
build() called: 6 glasses

## 3. What I saw in my experiments
- Activity 2 (moved _glasses++ outside setState): I tapped + and the number on the screen did not change. The count changed behind the scenes, but Flutter was never told to redraw the screen.
- Activity 3 (removed Expanded): That box stopped sharing the space equally. It shrank to fit only its own content, so the three boxes looked uneven.
- Activity 5 (changed the button corner from 8 to 20): The corners of the Elevated button became rounder.
 
## 4. Review answers
1. A StatelessWidget never changes after it is drawn. Example: ProfileCard. A StatefulWidget can change while the app runs. Example: WaterTrackerPage, because the glass count goes up and down.
2. The first class only creates the widget. The second class, called the State, keeps the data that changes, like _glasses, and draws the screen with build().
3. When _glasses++ was outside setState, the number changed in memory but the screen did not update. setState is what tells Flutter “my data changed, please redraw.”
4. build() is called when the screen first appears, and again every time setState is called. In the Debug Console, a new “build() called” line showed up after every tap.
5. In a Row, the main axis goes left to right and the cross axis goes up and down. In a Column, it is the opposite: the main axis goes top to bottom and the cross axis goes left to right.
6. Without Expanded, the box became only as wide as its own content, so the boxes were not equal. Expanded tells a widget to take the free space in the Row or Column, so the boxes share the width equally.
7. GridView.builder builds only the cards you can see on the screen, so the app stays fast even with a long list. A Column with many children would build all of them at once.
8. A Stack puts widgets on top of each other, like stickers. Positioned pins one of them to a spot, like top 8 and left 8. That is how the orange Best seller label sits in the corner of the card.
9. ThemeData styles the whole app at once. Example: elevatedButtonTheme in buildTheme() changes every Elevated button. A style on one widget changes only that widget. Example: the TextStyle on a single Text.
10. The State of ThemeDemoApp holds _isDark. When you flip the switch, it calls _setDark, which uses setState. Then MaterialApp is rebuilt, sees the new themeMode, and switches between the light and dark theme.