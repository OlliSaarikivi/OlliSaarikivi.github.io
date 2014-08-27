+++
title = "Reitit for Windows Phone 8.1"
date = 2014-08-26T10:49:35Z
collections = ["log", "reitit"]
+++

<img style="float: left; margin-right: 2em; margin-bottom: 1em;" src="/reitit.png"/>

Over the summer I have been developing a Windows Phone 8.1 version of my Helsinki metropolitan area route planner app, [Reitit](http://www.windowsphone.com/fi-fi/store/app/reitit/30e77f37-ef15-4860-b5d2-c4f7ee96f0e4). New features include:

- GPS tracking on the map
- A new more streamlined route listing
- Advanced search options

The new version is already mostly feature complete. However, the release of the app will be delayed due to problems I have encountered with the new framework:

1. The app is too slow. Page navigation is noticeably slower than in the old version. One optimization that I employed in the WP7 version was to not use databinding and instead create and update all controls in code-behind. I hoped that this would not be required to get smooth navigation on WP8 class hardware. I will have to do further testing to see what is causing the slow page loading.

2. The new [MapControl](http://msdn.microsoft.com/en-us/library/windows/apps/xaml/windows.ui.xaml.controls.maps.mapcontrol.aspx) for "Windows Phone XAML apps" has rendering issues when panning a map that includes UIElement pushpins. Basically the pushpins don't always move at the same speed as the rest of the map. When dragging a finger on the map, both the map image and the pushpins lag behind the touch point, but the map image itself lags *more* resulting in the pushpins not staying glued down on to the map.

The issue with the map control can be tolerated, as the map is otherwise quite a bit more beautiful than the old WP7 map. The page navigation issue, however, is something I will need to fix before publishing the new version.