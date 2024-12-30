# GetxRouting
class RouteName {
  static const loginpage = '/login';
  static const welcomepage = '/welcome';
}
========================================================================================================================


class Approutes {
  static List<GetPage> appRoutes() {
    return [
      GetPage(
        name: RouteName.welcomepage,
        page: () => Welcomepage(),
      ),
      GetPage(
        name: RouteName.loginpage,
        page: () => LoginpageScreen(),
      ),
    ];
  }
}
======================================================================================================

import 'package:flutter/material.dart';
import 'package:get/get.dart';

import 'Route/approutes.dart';
import 'Route/routename.dart';
import 'widgets/theme/mytheme.dart';

void main() {
  runApp(const MyApp());
}

class MyApp extends StatelessWidget {
  const MyApp({super.key});

  @override
  Widget build(BuildContext context) {
    return GetMaterialApp(
      themeMode: ThemeMode.system,
      theme: myTheme.lightTheme(context),
      darkTheme: myTheme.darkTheme(context),
      initialRoute: RouteName.welcomepage,
      getPages: Approutes.appRoutes(),
    );
  }
}


