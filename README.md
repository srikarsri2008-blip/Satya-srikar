import 'package:flutter/material.dart';

void main() {
  runApp(const AILifeAssistant());
}

class AILifeAssistant extends StatelessWidget {
  const AILifeAssistant({super.key});

  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      debugShowCheckedModeBanner: false,
      title: 'AI Life Assistant',
      theme: ThemeData(
        primarySwatch: Colors.blue,
      ),
      home: const DashboardScreen(),
    );
  }
}

class DashboardScreen extends StatelessWidget {
  const DashboardScreen({super.key});

  final List<Map<String, dynamic>> features = const [
    {"title": "AI Study Helper", "icon": Icons.school},
    {"title": "Resume Builder", "icon": Icons.description},
    {"title": "Expense Tracker", "icon": Icons.account_balance_wallet},
    {"title": "Fitness Planner", "icon": Icons.fitness_center},
    {"title": "Task Manager", "icon": Icons.task},
    {"title": "Content Creator", "icon": Icons.auto_awesome},
  ];

  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(
        title: const Text("AI Life Assistant"),
      ),
      body: Padding(
        padding: const EdgeInsets.all(16),
        child: GridView.builder(
          itemCount: features.length,
          gridDelegate:
              const SliverGridDelegateWithFixedCrossAxisCount(
            crossAxisCount: 2,
            crossAxisSpacing: 12,
            mainAxisSpacing: 12,
          ),
          itemBuilder: (context, index) {
            return Card(
              elevation: 5,
              child: InkWell(
                onTap: () {},
                child: Column(
                  mainAxisAlignment: MainAxisAlignment.center,
                  children: [
                    Icon(
                      features[index]["icon"],
                      size: 50,
                    ),
                    const SizedBox(height: 10),
                    Text(
                      features[index]["title"],
                      textAlign: TextAlign.center,
                      style: const TextStyle(
                        fontWeight: FontWeight.bold,
                      ),
                    ),
                  ],
                ),
              ),
            );
          },
        ),
      ),
    );
  }
}
