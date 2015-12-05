### SwiftView.xcodeproj - a curated Xcode view of Swift Source

This project is a simple means to navigate the Swift source tree including the
compiler sources and Swift standard library. 

git clone alongside your swift sources after it has been built and it should 
index/compile and be navigable with option-click as you would a normal Xcode project. 
The stdlib sources are viewable but not navigable as they are not built as I do not
know the secret sauce to build sources which are in module Swift inside Xcode. 

This is not intended to be a way to build Swift and will fail to link.
