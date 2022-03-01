TestFairy allows developers to log items with a session, without logging to the console output. In some cases, there are workarounds that allow you to wrap the TestFairy remote logging method in a way that will both log to the console and to the session.

<div data-duration-in="300" data-duration-out="100" class="docs-tabs w-tabs">
	<div class="docs-tabs-menu w-tab-menu" style="flex-wrap: wrap;">
		<a data-w-tab="tab-android" class="docs-tab w-inline-block w-tab-link w--current" style="margin: 2px;" href="#android">
			<div>Android</div>
		</a>
		<a data-w-tab="tab-ios" class="docs-tab w-inline-block w-tab-link" style="margin: 2px;" href="#ios">
			<div>iOS - Objective C</div>
		</a>
		<a data-w-tab="tab-ios-swift" class="docs-tab w-inline-block w-tab-link" style="margin: 2px;" href="#ios-swift">
			<div>iOS - Swift</div>
		</a>
		<a data-w-tab="tab-cordova" class="docs-tab w-inline-block w-tab-link" style="margin: 2px;" href="#cordova">
			<div>Cordova</div>
		</a>
		<a data-w-tab="tab-react-native" class="docs-tab w-inline-block w-tab-link" style="margin: 2px;" href="#react-native">
			<div>React Native</div>
		</a>
		<a data-w-tab="tab-nativescript" class="docs-tab w-inline-block w-tab-link" style="margin: 2px;" href="#nativescript">
			<div>Nativescript</div>
		</a>
		<a data-w-tab="tab-xamarin" class="docs-tab w-inline-block w-tab-link" style="margin: 2px;" href="#xamarin">
			<div>Xamarin</div>
		</a>
		<a data-w-tab="tab-unity" class="docs-tab w-inline-block w-tab-link" style="margin: 2px;" href="#unity">
			<div>Unity</div>
		</a>
		<a data-w-tab="tab-adobe-air" class="docs-tab w-inline-block w-tab-link" style="margin: 2px;" href="#adobe-air">
			<div>Adobe Air</div>
		</a>
		<a data-w-tab="tab-titanium" class="docs-tab w-inline-block w-tab-link" style="margin: 2px;" href="#titanium">
			<div>Titanium</div>
		</a>
	</div>

	<div class="docs-tabs-content w-tab-content">
		<div data-w-tab="tab-android" class="w-tab-pane w--tab-active">
			<h3>Syntax</h3>
      <p>
				<code>TestFairy.log("&lt;tag&gt;", "&lt;message&gt;");</code><br />
      </p>

      <h3>Code Example</h3>
      <pre>
// Be sure to import TestFairy
import com.testfairy.TestFairy;

TestFairy.log("Tag", "Hello, TestFairy!");
      </pre>
		</div>

		<div data-w-tab="tab-ios" class="w-tab-pane">
			<h3>Syntax</h3>
      <p>
				<code>TFLog(@"&lt;message with format&gt;", &lt;arguments&gt;);</code><br />
				<code>[TestFairy log:@"&lt;message&gt;"];</code><br />
      </p>

      <h3>Code Example</h3>
      <pre>
// Be sure to import TestFairy
#import "TestFairy.h"

TFLog(@"Hello, %@", @"TestFairy!");
[TestFairy log:@"Hello, TestFairy!"];
      </pre>

			<p>We recommend sending all calls to <code>NSLog</code> to TestFairy so you can continue to use <code>NSLog</code> and see all your log statements in your session.</p>
			<p>To enable sending logs to TestFairy, you will have to redefine <code>NSLog</code> using a macro with the following lines tThis macro allows you to continue using <code>NSLog</code> in your code, while also adding the logs to the  matching session in TestFairy).</p>

			<p><strong>Changing Your Prefix Header</strong></p>
			<pre><code class=" hljs cs"><span class="hljs-preprocessor">#import "TestFairy.h"</span>
<span class="hljs-preprocessor">#<span class="hljs-keyword">define</span> NSLog(s, ...) do { NSLog(s, ##__VA_ARGS__); TFLog(s, ##__VA_ARGS__); } while (0)</span>
</code></pre>
			<ol>
			<li>Add the above line to a global header in your project, accessible to every class file.</li>
			<li>Update or create a Prefix Header (.pch) for your project. If you do not have a PCH file in your project, you can follow the steps in the next section.</li>
			</ol>
			<p><strong>Creating a New Prefix Header</strong></p>
			<p>If your project doesn’t already include a Prefix Header (.pch):<br></p>
			<ol>
				<li>Create a new file under iOS &gt; Other &gt; PCH File.</li>
				<li>Name your file “PCH file”.</li>
				<li>Add these lines of code to the file:<br>
				<code>#import "TestFairy.h"<br/>
				#define NSLog(s, ...) do { NSLog(s, ##__VA_ARGS__); TFLog(s, ##__VA_ARGS__); } while (0)</code></li>
				<li><p>From the <b>Project Navigator</b>, select your project and the corresponding target.</p></li>
				<li><p>Project &gt; Build Settings &gt; Search: "Prefix Header".</p></li>
				<li><p>Under <b>Apple LLVM 7.0" you will get the Prefix Header key.</p></li>
				<li><p>Type the path of the file, for example: "$(SRCROOT)/$(PROJECT_NAME)/ProjectName-Prefix.pch". Please note that your file may be at a different location.</p></li>
				<li><p>Make sure the option "Precompile Prefix Header" is set to YES.</p></li>
				<li><p>Clean your project, and rebuild.</p></li>
			</ol>
		</div>

		<div data-w-tab="tab-ios-swift" class="w-tab-pane">
			<h3>Syntax</h3>
      <p>
				<b>TestFairy.log("&lt;message&gt;")</b><br />
      </p>

      <h3>Code Example</h3>
      <pre>
TestFairy.log("Hello, TestFairy!")
      </pre>

			<p>We recommend wrapping all <code>print</code> statements with a custom method, which will output to both the console and to TestFairy sessions. One suggestion we have is to create a new file named <code>TestFairyLog.swift</code> in your source path, and add the following to the contents of the file:</p>
<pre><code class="swift">//
//  TestFairyLog.swift
//
//  Copyright © TestFairy. All rights reserved.
//

import Foundation

public func print(_ items: Any..., separator: String = " ", terminator: String = "\n") {
	let output = items.map { "\($0)" }.joined(separator: separator)
	TestFairy.log(output)
	Swift.print(output, terminator: terminator)
}
</code></pre>
			<p>This will print any output to both the Xcode console, and to the active session on TestFairy.</p>
		</div>

		<div data-w-tab="tab-cordova" class="w-tab-pane">
			<h3>Syntax</h3>
      <p>
				<codeTestFairy.log("&lt;message&gt;");</code><br />
      </p>

      <h3>Code Example</h3>
      <pre>
TestFairy.log("Hello, TestFairy!");
      </pre>

			<p>We recommend wrapping all <b>log</b> statements with a custom method, which will output to both the console and to TestFairy sessions. One suggestion we have is to add a method that looks like this:</p>
			<pre>
var testfairyConsoleLog = console.log;
console.log = function(message) {
	testfairyConsoleLog(message);
	TestFairy.log(message);
}
			</pre>
		</div>

		<div data-w-tab="tab-react-native" class="w-tab-pane">
			<h3>Syntax</h3>
      <p>
				<code>TestFairy.log("&lt;message&gt;");</code><br />
      </p>

      <h3>Code Example</h3>
      <pre>
// Be sure to import TestFairy
const TestFairy = require('react-native-testfairy');

TestFairy.log("Hello, TestFairy!");
      </pre>

			<p>We recommend wrapping all <code>log</code> statements with a custom method, which will output to both the console and to TestFairy sessions. One suggestion we have is to add a method that looks like this:</p>
			<pre>
var testfairyConsoleLog = console.log;
console.log = function(message) {
	testfairyConsoleLog(message);
	TestFairy.log(message);
}
			</pre>
		</div>


		<div data-w-tab="tab-nativescript" class="w-tab-pane">
			<h3>Syntax</h3>
      <p>
				<code>TestFairySDK.log("&lt;message&gt;");</code><br />
      </p>

      <h3>Code Example</h3>
      <pre>
// Be sure to import TestFairy
import { TestFairySDK } from 'nativescript-testfairy';

TestFairySDK.log("Hello, TestFairy!");
      </pre>

			<p>We recommend wrapping all <code>log</code> statements with a custom method, which will output to both the console and to TestFairy sessions. One suggestion we have is to add a method that looks like this:</p>
			<pre>
var testfairyConsoleLog = console.log;
console.log = function(message) {
	testfairyConsoleLog(message);
	TestFairySDK.log(message);
}
			</pre>
		</div>

		<div data-w-tab="tab-xamarin" class="w-tab-pane">
			<p>We recommend wrapping all <code>TFLog</code> statements with a custom method, which will output to both the console and to TestFairy sessions. One suggestion we have is to add a method that looks like this:</p>

      <h3>Code Example</h3>

      <pre>
// Be sure to import TestFairy
using TestFairyLib;

public static void Log(string format, params object[] arg)
{
    using (var nsFormat = new NSString(string.Format(format, arg)))
    {
        CFunctions.TFLog(nsFormat.Handle, "");
        Console.WriteLine(string.Format(format, arg));
    }
}
      </pre>

			<p>Now, you can log statements using this call:</p>
			<pre>
Log("Hello {0}", "World");
			</pre>
		</div>

		<div data-w-tab="tab-unity" class="w-tab-pane">
			<h3>Syntax</h3>
      <p>
				<code>TestFairy.log("&lt;message&gt;");</code><br />
      </p>

      <h3>Code Example</h3>
      <pre>
// Be sure to import TestFairy
using TestFairyUnity;

TestFairy.log("Hello, TestFairy!");
      </pre>
		</div>

		<div data-w-tab="tab-adobe-air" class="w-tab-pane">
			<h3>Syntax</h3>
      <p>
				<code>AirTestFairy.log("&lt;message&gt;");</code><br />
      </p>

      <h3>Code Example</h3>
      <pre>
// Be sure to import TestFairy
import com.testfairy.AirTestFairy;

AirTestFairy.log("Hello, TestFairy!");
      </pre>
		</div>

		<div data-w-tab="tab-titanium" class="w-tab-pane">
			<h3>Syntax</h3>
      <p>
				<code>TiTestFairy.log("&lt;message&gt;");</code><br />
      </p>

      <h3>Code Example</h3>
      <pre>
// Be sure to import TestFairy
var TiTestFairy = require('com.testfairy.titestfairy');

TiTestFairy.log("Hello, TestFairy!");
      </pre>
		</div>

	</div>
</div>
