---
title: স্টেটফুলসেট
id: statefulset
date: 2018-04-12
full_link: /bn/docs/concepts/workloads/controllers/statefulset/
short_description: >
  একটি স্টেটফুলসেট প্রতিটি পডের জন্য টেকসই স্টোরেজ এবং ক্রমাগত শনাক্তকারী সহ পডের একটি সেট ডিপ্লয়মেন্ট এবং স্কেলিং পরিচালনা করে।

aka: 
tags:
- fundamental
- core-object
- workload
- storage
---
 এটি একটি {{< glossary_tooltip text="পড" term_id="pod">}} সেটের ডিপ্লয়মেন্ট এবং স্কেলিং পরিচালনা করে , এবং পডগুলির *ক্রম এবং অনন্যতা সম্পর্কে গ্যারান্টি প্রদান করে* ৷  

<!--more--> 

যেমন একটি {{< glossary_tooltip term_id="deployment" >}}, একটি স্টেটফুলসেট পডগুলি পরিচালনা করে যা একটি অভিন্ন কন্টেইনার স্পেকের উপর ভিত্তি করে। একটি ডিপ্লয়মেন্টের থেকে ভিন্ন, একটি স্টেটফুলসেট তার প্রতিটি পডের জন্য একটি স্টিকি পরিচয় বজায় রাখে। এই পডগুলি একই স্পেক (spec) থেকে তৈরি করা হয়েছে, কিন্তু বিনিময়যোগ্য নয়: প্রতিটিরই একটি ক্রমাগত শনাক্তকারী থাকে যা এটি যেকোনো রিশিডিউলিং জুড়ে বজায় রাখে।

আপনি যদি আপনার ওয়ার্কলোডের জন্য পার্সিস্টেন্স (persistence) প্রদান করতে স্টোরেজ ভলিউম ব্যবহার করতে চান, আপনি সমাধানের অংশ হিসাবে স্টেটফুলসেট ব্যবহার করতে পারেন। যদিও স্টেটফুলসেটে পৃথক পড ব্যর্থতার জন্য সংবেদনশীল, ক্রমাগত পড শনাক্তকারী নতুন পডের সাথে বিদ্যমান ভলিউমগুলিকে মেলানো সহজ করে তোলে যা ব্যর্থ হয়েছে এমন যেকোনোটি প্রতিস্থাপন করে।
