### Does TestFairy work in production with live traffic?

Yes. TestFairy works both in testing and in production. However, before doing that, please read this document carefully.

When running TestFairy in production, you may record sensitive data such as medical information, financial data or photos.

Therefore it is important to follow these guidelines:

1. On iOS, you **must** request explicit user consent before recording start.
Please read carefully the [Apple guidelines](https://developer.apple.com/app-store/review/guidelines/) and pay special attention to section 2.5.14

2. On Android, you **must** use [TestFairy Production SDK](https://docs.testfairy.com/Android/Production_SDK.html) to comply with [Play Store Developer Distribution Agreement](https://play.google.com/about/developer-distribution-agreement.html).

3. When recording sensitive data you **must** use TestFairy's [end-to-end encryption](/Security/End_to_End_Data_Encryption.html) with your own private keys, so that only your team will be able to see your sessions.

4. You **must** [hide sensitive data](/SDK/Hiding_Sensitive_Data.html) such as credit card numbers, passwords, or other PII, so that this info will not be uploaded to the server.

5. It is strongly recomended to use a [private cloud](/Security/Private_Cloud.html) .

6. In case you are using TestFairy for customer support to better understand your users in case of a technical issue,
it is recomended to add a button to your app menu (call it "advanced support"?) and have that button call `TestFairy.begin()`.
Before calling `begin()` ask the user if this is ok to record their screen for quality assurance purposes.
When doing that, make sure that session duration is set to 2-3 minutes, just enough to identify the cause of a problem.

7. You **must** include a proper disclaimer in your app terms of service document.
You must explain exactly what data you collect, and how to request deletion of that data.
For more information about [GDPR](/Security/GDPR.html), please [contact the TestFairy team](https://testfairy.com/contact)

8. Please make sure never to use TestFairy Auto-update with apps that are shipped to production. This is a clear violation of both Apple and Google's terms.
