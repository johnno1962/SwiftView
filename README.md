
### SwiftView.xcodeproj - a curated Xcode view of Swift Source

I used this project when Swift first came out as it would index and I could find may way
around the Swift sources much more easilly. It is now deprecated in favour of the
supported way of generating a Swift.xcodeproj wihch is using the command:

```
utils/build-script --release-debuginfo --xcode
```
Your milage may vary. I find that due to timing issues with generated files you may have
to repeat this build command a few times until all sources are generated and the errors
start repeating at which point you may need to make the following links:

```
ln -s x86_64 ../build/Xcode-RelWithDebInfoAssert/swift-macosx-x86_64/stdlib/public/stubs/Swift.build/RelWithDebInfo/swiftStdlibStubs-macosx-x86_64.build/Objects-normal/undefined_arch
ln -s x86_64 ../build/Xcode-RelWithDebInfoAssert/swift-macosx-x86_64/stdlib/public/runtime/Swift.build/RelWithDebInfo/swiftRuntime-macosx-x86_64.build/Objects-normal/undefined_arch
```
When it completes, open `../build/Xcode-RelWithDebInfoAssert/swift-macosx-x86_64/Swift.scodeproj`
and you'll be able to debug the swift compiler, setting breakpoints and singlstepping
like a normal program which is inredibly useful. When you first open the project there
are so many targets Xcode will ask if you want to manage schemes manually;
select and create a scheme for target "swift" set the execution arguments 
and you're in business.

Old README:

This project is a simple means to navigate the Swift source tree including the
compiler sources and Swift standard library. 

git clone alongside your swift sources after it has been built and it should 
index/compile and be navigable with option-click as you would a normal Xcode project. 
Adjust the symbolic link "build" to your current build directory to find the headers.
The stdlib sources are viewable but not navigable as they are not built as I do not
know the secret sauce to build sources which are in module Swift inside Xcode.

This is not intended to be a way to build Swift and will fail to link.
