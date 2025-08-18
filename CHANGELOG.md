## 5.5.1
- Fixed a bug in `computeMaxIntrinsicHeight` of `TableView`.

## 5.5.0
- New `ExpandableTableRow` widget.
- New `TableRowAnimatedSize` widget.
- New `popupCellPadding` functionality for the `TableColumnControlHandlesPopupRoute`.
- New `physicsHorizontal` argument for the `TableView` and `SliverTableView`.

## 5.4.0
- New `shrinkWrapHorizontal` argument of the `TableView.builder` constructor. 
- New `tableOverlayBuilder` and `columnOverlayBuilder` of the `TableColumnControlHandlesPopupRoute.realtime`
  constructor.
- `TableView` now supports intrinsic width.

## 5.3.0
- New `shrinkWrapVertical` argument of the `TableView.builder` constructor.
- Fixed a bug introduced in `5.2.0` which caused extra space being left for header or footer even when
  none are specified.
- Fixed a bug with header and footer painting outside the area of the `TableView`.

## 5.2.0
- New support for optional `rowHeight` along with `rowHeightBuilder` and `rowPrototype` for `SliverTableView`,
  matching the functionality of the `TableView`.
- `SliverTableView` no longer stops existing when leaving visible area. Although this behavior matches more closely
  with other slivers, it can introduce more unnecessary overhead when many are used.
- New `physics` `TableView` constructor argument.
- New ability to completely disable horizontal (header and/or footer) dividers.
- Fixed visual inconsistency when `TableView` or `SliverTableView` are used outside of `SafeArea` (scrollbar is no
  longer appears detached on some devices that have "unsafe" bottom side).
- Fixed visual inconsistency when the column being moved would get clipped when changing places with a frozen one
  when the vertical divider is not visible.
- Fixed visual inconsistency when the column being moved would get painted below others.
- Enabled semantics on debug builds when row reordering is used (previously disabled in this case).
- Greatly optimized performance.

## 5.1.0
- New support for optional `rowHeight` along with `rowHeightBuilder` and `rowPrototype` for `TableView`.
- `wigglesPerRow` of `TableViewStyle` is now deprecated. Use functionally the same `wiggleCount` instead.
- Updated example.
- Updated README.

## 5.0.2
- Improved error messages when widget not supported in the table row attempts to paint.
- Updated README to better explain the importance of wrapping table rows with unsupported widgets.

## 5.0.1
- Fixed color precision warnings.
- Updated example Android project.
- Updated README.

## 5.0.0
- New row reordering feature.
- BREAKING: Changed the default scrollbar style values to the Flutter defaults. To restore previous behavior use the following style:
  ```dart
  TableViewScrollbarsStyle.symmetric(
    TableViewScrollbarStyle(
      interactive: true,
      thumbVisibility: WidgetStatePropertyAll(true),
      trackVisibility: WidgetStatePropertyAll(true),
    ),
  )
  ```
- BREAKING: `AutomaticKeepAlive`s are no longer added in for table rows by default. To restore previous behavior set the `addAutomaticKeepAlives` constuctor argument to `true`.

## 4.0.2
- Fix `TableView` overscroll notification silencing preventing `RefreshIndicator` from functioning.
- Changed color of the default placeholder from deprecated `colorScheme.background` to `colorScheme.surface`.
- Updated package metadata and README.

## 4.0.1
- Updated package description.

## 4.0.0
- New column controls feature introduced. `TableColumnControlHandlesPopupRoute`
  that displays custom popup as well as column control handles over the table
  that allow user to resize and reorder columns.
- Introduced RTL layout support.
- Removed deprecated `scrollPadding` argument of the `TableView` and `SliverTableView` constructors.
- Fix previously ignored by the `SliverTableView` `bodyContainerBuilder` argument to work the same way as does its
  `TableView` counterpart.
- `ShimmerPlaceholderShadeProvider`'s state now correctly calls `super.dispose` method.
- Minor performance enhancements.

## 3.4.0

- New `flex` property of the `TableColumn` implemented.
- New vertical divider reveal animation customization options implemented.
- Other minor fixes and improvements,

## 3.3.1

- Improved compatibility with different versions of Flutter.

## 3.3.0

- BREAKING VISUALS: TableView is not using divider style inferred from the `Divider` widget by default.
- New: `TableView`s and `SliverTableView`s constructor argument `style` that allows granular customization of how
  a table is displayed.
- Deprecated: `TableView`s and `SliverTableView`s constructor argument `scrollPadding` has been deprecated in favor
  of analogous attribute in the style.

## 3.2.1

- Fixed: `SliverTableView`'s horizontal offset not resetting when using a sticky frozen column.

## 3.2.0

- `sticky` property of a `TableColumn` implemented.
- Table cell hit detection bug fixed.

## 3.1.3

- Screenshots updated.

## 3.1.2

- README updated.

## 3.1.1

- `SliverTableView` hit detection bug fixed.
- README updated.

## 3.1.0

- `SliverTableView` introduced.

## 3.0.2

- Fix a bug leading to a memory leak and perpetual exceptions in debug mode
  when the table is disposed separately from the `placeholderShade` used by it.

## 3.0.1

- Documentation comments and static analysis fixes.

## 3.0.0

- Substantial performance improvements.
- Rows and cells are no longer rebuilt on horizontal scroll.
- Cell widgets no longer lose state when transitioning between
  scrolled and fixed state.
- Both regular and placeholder row widgets are now built in the same
  hierarchy meaning that both types of row widgets will share
  a state as long as their types and keys match.
  Thanks to that, `GlobalKey` and `RepaintBoundary` hacks are
  no longer required to implement transitions between them
- Limitations on the usage of certain widgets for wrapping rows
  are introduced because of intrusive optimizations. Refer to
  [the README section](https://github.com/NikolayNIK/material_table_view#row-wrapping-widgets-restriction)
  for more information.
- Deprecated `placeholderContainerBuilder` `TableView` constructor
  parameter is removed. Use `placeholderShade` described below to
  implement placeholder shading.
- `placeholderShade` parameter introduced in a `TableView.builder`
  constructor which can be used to implement placeholder shading.
- Deprecated default constructor of `TableView` is removed.
- `dividerRevealOffset` property of a `TableView.builder` constructor is now removed.

## 2.1.3

- Deprecations and warnings fixes.

## 2.1.2

- Placeholder system is now deprecated and scheduled to be removed in the next
  major release to allow for further optimization and feature development.
  It is advised to use the [approach](https://docs.flutter.dev/cookbook/effects/shimmer-loading#paint-one-big-shimmer)
  suggested in the official docs instead.

## 2.1.1

- Minor bug fixes and improvements.

## 2.1.0

- New `bodyContainerBuilder` property implemented.

## 2.0.0

- Existing nameless `TableView` constructor is now deprecated and no longer constant
  but otherwise works the same.
- New named `TableView.builder` constructor added in which
  decorators are removed in favor of row-building function returning a widget
  built with the help of a closure passed as an argument.
- Performance improvements.

## 1.0.2

- Fix name conflict of ListenableBuilder widget with upcoming SDK counterpart.
- Included demo project as an example.
- README changes.

## 1.0.1

- README and pubspec changes.

## 1.0.0

- Initial release.
