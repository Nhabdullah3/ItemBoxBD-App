# ItemBox BD Android App (Website wrapper)

এই প্রজেক্টটি ItemBox BD ওয়েবসাইটকে Android অ্যাপের মধ্যে চালায়। ওয়েবসাইটের বর্তমান product/order flow-ই ব্যবহার করবে, তাই আলাদা করে customer details/order API পুনরায় বানানো হয়নি।

## APK তৈরির ধাপ
1. ZIP ফাইল extract করুন।
2. Android Studio খুলে `ItemBoxBD_WebView_Android` ফোল্ডার Open করুন।
3. Gradle Sync সম্পন্ন করুন; JDK 17 ও Android SDK 35 ইনস্টল থাকতে হবে।
4. Run দিয়ে emulator/ফোনে পরীক্ষা করুন।
5. APK: `Build > Build Bundle(s) / APK(s) > Build APK(s)`.
6. Play Store-এর জন্য `Build > Generate Signed Bundle / APK > Android App Bundle (AAB)` ব্যবহার করুন.

## গুরুত্বপূর্ণ
এই পরিবেশে Android SDK/Gradle build toolchain নেই, তাই ZIP-এ source code আছে কিন্তু compiled APK তৈরি হয়নি. Android Studio-তে build করতে হবে. Play Store-এ প্রকাশের আগে privacy policy, Data safety, app icon/screenshots এবং Play Console-এর বর্তমান নিয়ম পূরণ করুন.

## Android Studio ছাড়াই Cloud-এ APK build
এই ZIP-এ GitHub Actions workflow যোগ করা আছে। GitHub-এ নতুন repository তৈরি করে ZIP-এর ফাইলগুলো upload/push করুন। এরপর repository-এর **Actions** tab-এ `Build ItemBox BD APK` workflow চালান। কাজ সফল হলে run-এর নিচে **Artifacts** অংশ থেকে `ItemBoxBD-debug-apk` ডাউনলোড করা যাবে। এটি debug APK; Play Store-এর জন্য signed AAB আলাদাভাবে তৈরি করতে হবে।
