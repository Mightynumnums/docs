TestFairy can collect additional information from your session, which can help you generate better insights.

<div data-duration-in="300" data-duration-out="100" class="docs-tabs w-tabs">
	<div class="docs-tabs-menu w-tab-menu" style="flex-wrap: wrap;">
		<a data-w-tab="tab-android" class="docs-tab w-inline-block w-tab-link w--current" style="margin: 2px;" href="#android">
			<div>Android</div>
		</a>
		<a data-w-tab="tab-ios" class="docs-tab w-inline-block w-tab-link" style="margin: 2px;" href="#ios">
			<div>iOS</div>
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
				<code>TestFairy.setAttribute("&lt;key&gt;", "&lt;value&gt;");</code><br />
      </p>

			<p>The first value is a string <code>key</code> to help you search for the attribute in your session. The second parameter, <code>value</code>, is any string value for the attribute associated with the session. Neither value can be nil. These attributes are available later in the session recording page, are available via API, and are searchable.</p>

      <h3>Code Example</h3>
      <pre>
// Be sure to import TestFairy
import com.testfairy.TestFairy;

TestFairy.setAttribute("payment-method","free");
TestFairy.setAttribute("account-type","driver");
TestFairy.setAttribute("phone","+1-672-154-5109");
TestFairy.setAttribute("level","20");

      </pre>
		</div>

		<div data-w-tab="tab-ios" class="w-tab-pane">
			<h3>Syntax</h3>
      <p>
				<code>[TestFairy setAttribute:@"&lt;key&gt;" withValue:@"&lt;value&gt;"];</code><br />
      </p>

			<p>The first value is a string <b>key</b> to help you search for the attribute in your session. The second parameter, <code>value</code>, is any string value for the attribute associated with the session. Neither value can be nil. These attributes are available later in the session recording page, are available via API, and are searchable.</p>

      <h3>Code Example</h3>
      <pre>
// Be sure to import TestFairy
#import "TestFairy.h"

[TestFairy setAttribute:@"name" withValue:@"John Snow"];
[TestFairy setAttribute:@"phone" withValue:@"+672-14-5109"];
[TestFairy setAttribute:@"age" withValue:@"20"];
[TestFairy setAttribute:@"favorite_color" withValue:@"blue"];
      </pre>
		</div>

		<div data-w-tab="tab-cordova" class="w-tab-pane">
			<h3>Syntax</h3>
      <p>
				<code>TestFairy.setAttribute("&lt;key&gt;", "&lt;value&gt;");</code><br />
      </p>

			<p>The first value is a string <code>key</code> to help you search for the attribute in your session. The second parameter, <code>value</code>, is any string value for the attribute associated with the session. Neither value can be nil. These attributes are available later in the session recording page, are available via API, and are searchable.</p>

      <h3>Code Example</h3>
      <pre>
TestFairy.setAttribute("name","John Snow");
TestFairy.setAttribute("phone","+672-14-5109");
TestFairy.setAttribute("age","20");
TestFairy.setAttribute("favorite_color","blue");
      </pre>
		</div>

		<div data-w-tab="tab-react-native" class="w-tab-pane">
			<h3>Syntax</h3>
      <p>
				<code>TestFairy.setAttribute("&lt;key&gt;", "&lt;value&gt;");</code><br />
      </p>

			<p>The first value is a string <b>key</b> to help you search for the attribute in your session. The second parameter, <code>value</code>, is any string value for the attribute associated with the session. Neither value can be nil. These attributes are available later in the session recording page, are available via API, and are searchable.</p>

      <h3>Code Example</h3>
      <pre>
// Be sure to import TestFairy
const TestFairy = require('react-native-testfairy');

TestFairy.setAttribute("name","John Snow");
TestFairy.setAttribute("phone","+672-14-5109");
TestFairy.setAttribute("age","20");
TestFairy.setAttribute("favorite_color","blue");
      </pre>
		</div>


		<div data-w-tab="tab-nativescript" class="w-tab-pane">
			<h3>Syntax</h3>
      <p>
				<code>TestFairySDK.setAttribute("&lt;key&gt;", "&lt;value&gt;");</code><br />
      </p>

			<p>The first value is a string <code>key</code> to help you search for the attribute in your session. The second parameter, <code>value</code>, is any string value for the attribute associated with the session. Neither value can be nil. These attributes are available later in the session recording page, are available via API, and are searchable.</p>

      <h3>Code Example</h3>
      <pre>
// Be sure to import TestFairy
import { TestFairySDK } from 'nativescript-testfairy';

TestFairySDK.setAttribute("name","John Snow");
TestFairySDK.setAttribute("phone","+672-14-5109");
TestFairySDK.setAttribute("age","20");
TestFairySDK.setAttribute("favorite_color","blue");
      </pre>
		</div>

		<div data-w-tab="tab-xamarin" class="w-tab-pane">
			<h3>Syntax</h3>
      <p>
				<code>TestFairy.SetAttribute ("&lt;key&gt;", "&lt;value&gt;");</code><br />
      </p>

			<p>The first value is a string <code>key</code> to help you search for the attribute in your session. The second parameter, <code>value</code>, is any string value for the attribute associated with the session. Neither value can be nil. These attributes are available later in the session recording page, are available via API, and are searchable.</p>

      <h3>Code Example</h3>
      <pre>
// Be sure to import TestFairy
using TestFairyLib;

TestFairy.SetAttribute ("name","John Snow");
TestFairy.SetAttribute ("phone","+672-14-5109");
TestFairy.SetAttribute ("age","20");
TestFairy.SetAttribute ("favorite_color","blue");
      </pre>
		</div>

		<div data-w-tab="tab-unity" class="w-tab-pane">
			<h3>Syntax</h3>
      <p>
				<code>TestFairy.setAttribute("&lt;key&gt;", "&lt;value&gt;");</code><br />
      </p>

			<p>The first value is a string <code>key</code> to help you search for the attribute in your session. The second parameter, <code>value</code>, is any string value for the attribute associated with the session. Neither value can be nil. These attributes are available later in the session recording page, are available via API, and are searchable.</p>

      <h3>Code Example</h3>
      <pre>
// Be sure to import TestFairy
using TestFairyUnity;

TestFairy.setAttribute("name","John Snow");
TestFairy.setAttribute("phone","+672-14-5109");
TestFairy.setAttribute("age","20");
TestFairy.setAttribute("favorite_color","blue");
      </pre>
		</div>

		<div data-w-tab="tab-adobe-air" class="w-tab-pane">
			<h3>Syntax</h3>
      <p>
				<code>AirTestFairy.setAttribute("&lt;key&gt;", "&lt;value&gt;");</code><br />
      </p>

			<p>The first value is a string <code>key</code> to help you search for the attribute in your session. The second parameter, <code>value</code>, is any string value for the attribute associated with the session. Neither value can be nil. These attributes are available later in the session recording page, are available via API, and are searchable.</p>

      <h3>Code Example</h3>
      <pre>
// Be sure to import TestFairy
import com.testfairy.AirTestFairy;

AirTestFairy.setAttribute("name","John Snow");
AirTestFairy.setAttribute("phone","+672-14-5109");
AirTestFairy.setAttribute("age","20");
AirTestFairy.setAttribute("favorite_color","blue");
      </pre>
		</div>

		<div data-w-tab="tab-titanium" class="w-tab-pane">
			<h3>Syntax</h3>
      <p>
				<code>TiTestFairy.setAttribute("&lt;key&gt;", "&lt;value&gt;");</code><br />
      </p>

			<p>The first value is a string <code>key</code> to help you search for the attribute in your session. The second parameter, <code>value</code>, is any string value for the attribute associated with the session. Neither value can be nil. These attributes are available later in the session recording page, are available via API, and are searchable.</p>

      <h3>Code Example</h3>
      <pre>
// Be sure to import TestFairy
var TiTestFairy = require('com.testfairy.titestfairy');

TiTestFairy.setAttribute("name","John Snow");
TiTestFairy.setAttribute("phone","+672-14-5109");
TiTestFairy.setAttribute("age","20");
TiTestFairy.setAttribute("favorite_color","blue");
      </pre>
		</div>

	</div>
</div>

Adding these lines will mark this session with the values above, so when you review the recording, you have more information about the person running the app.

## Notes

* `setAttribute` may be called many times.
* You may call `setAttribute` before or after `begin`.
* You can only store a maximum of 64 keys. The keys can be a maximum of 64 characters. The values can have a maximum of 1000 characters.
