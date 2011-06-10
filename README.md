# NSAlert-SynchronousSheet

NSAlert-SynchronousSheet offers a category on `NSAlert` to run alerts synchronously as sheets. That is, you can begin a sheet and then wait for it to complete like you would for an application-modal dialog. This is often more convenient than designing your code for asynchronous callbacks.

The code should be thread-safe: beginning and ending the alert is performed synchronously on the main thread.

The code is used in [Renamer](http://renamer.com).


## Usage

Import the category in the classes where you want to run synchronous alert sheets:

	#import "NSAlert+SynchronousSheet.h"
	
To run an alert as a sheet on the main window:

	NSAlert *alert = ...   // create alert in the usual way
	NSInteger result = [alert runModalSheet];
	
To run an alert as a sheet on some other window:

	NSAlert *alert = ...   // create alert in the usual way
	NSInteger result = [alert runModalSheetForWindow:aWindow];

In both cases result contains the button clicked (`NSAlertFirstButtonReturn`, ...); see the [Apple docs](http://developer.apple.com/library/mac/documentation/Cocoa/Reference/ApplicationKit/Classes/NSAlert_Class/Reference/Reference.html#//apple_ref/doc/uid/20002032-SW2) for more details.


## License

Copyright (c) 2011, Incredible Bee Ltd. All rights reserved.

Redistribution and use in source and binary forms, with or without modification, are permitted provided that the following conditions are met:

- Redistributions of source code must retain the above copyright notice, this list of conditions and the following disclaimer.
- Redistributions in binary form must reproduce the above copyright notice, this list of conditions and the following disclaimer in the documentation and/or other materials provided with the distribution.
- Neither the name of the Incredible Bee Ltd. nor the names of its contributors may be used to endorse or promote products derived from this software without specific prior written permission.

THIS SOFTWARE IS PROVIDED BY THE COPYRIGHT HOLDERS AND CONTRIBUTORS "AS IS" AND ANY EXPRESS OR IMPLIED WARRANTIES, INCLUDING, BUT NOT LIMITED TO, THE IMPLIED WARRANTIES OF MERCHANTABILITY AND FITNESS FOR A PARTICULAR PURPOSE ARE DISCLAIMED. IN NO EVENT SHALL INCREDIBLE BEE LTD. BE LIABLE FOR ANY DIRECT, INDIRECT, INCIDENTAL, SPECIAL, EXEMPLARY, OR CONSEQUENTIAL DAMAGES (INCLUDING, BUT NOT LIMITED TO, PROCUREMENT OF SUBSTITUTE GOODS OR SERVICES; LOSS OF USE, DATA, OR PROFITS; OR BUSINESS INTERRUPTION) HOWEVER CAUSED AND ON ANY THEORY OF LIABILITY, WHETHER IN CONTRACT, STRICT LIABILITY, OR TORT (INCLUDING NEGLIGENCE OR OTHERWISE) ARISING IN ANY WAY OUT OF THE USE OF THIS SOFTWARE, EVEN IF ADVISED OF THE POSSIBILITY OF SUCH DAMAGE.