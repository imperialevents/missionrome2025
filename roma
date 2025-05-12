// App.js
import React from 'react';
import { Text, View, Button } from 'react-native';
import { NavigationContainer } from '@react-navigation/native';
import { createBottomTabNavigator } from '@react-navigation/bottom-tabs';
import { createNativeStackNavigator } from '@react-navigation/native-stack';
import { Ionicons } from '@expo/vector-icons';

const Tab = createBottomTabNavigator();
const Stack = createNativeStackNavigator();

function HomeScreen({ navigation }) {
  return (
    <View style={{ flex: 1, justifyContent: 'center', alignItems: 'center' }}>
      <Text>Welcome to the Rome Game!</Text>
      <Button title="Start Mission" onPress={() => navigation.navigate('Mission')} />
    </View>
  );
}

function MissionScreen({ navigation }) {
  return (
    <View style={{ flex: 1, justifyContent: 'center', alignItems: 'center' }}>
      <Text>Your mission: Find the Trevi Fountain!</Text>
      <Button title="Mission Complete" onPress={() => navigation.navigate('MissionComplete')} />
    </View>
  );
}

function MissionCompleteScreen() {
  return (
    <View style={{ flex: 1, justifyContent: 'center', alignItems: 'center' }}>
      <Text>Well done! You completed the mission!</Text>
    </View>
  );
}

function MapScreen() {
  return <CenterText text="Map Screen (coming soon)" />;
}
function CameraScreen() {
  return <CenterText text="Camera Screen (coming soon)" />;
}
function RewardsScreen() {
  return <CenterText text="Rewards Screen (coming soon)" />;
}
function ProfileScreen() {
  return <CenterText text="Profile Screen (coming soon)" />;
}

function CenterText({ text }) {
  return (
    <View style={{ flex: 1, justifyContent: 'center', alignItems: 'center' }}>
      <Text>{text}</Text>
    </View>
  );
}

function HomeStack() {
  return (
    <Stack.Navigator>
      <Stack.Screen name="HomeMain" component={HomeScreen} options={{ headerShown: false }} />
      <Stack.Screen name="Mission" component={MissionScreen} />
      <Stack.Screen name="MissionComplete" component={MissionCompleteScreen} options={{ presentation: 'modal' }} />
    </Stack.Navigator>
  );
}

export default function App() {
  return (
    <NavigationContainer>
      <Tab.Navigator
        screenOptions={({ route }) => ({
          tabBarIcon: ({ focused, color, size }) => {
            let iconName;

            if (route.name === 'Home') iconName = focused ? 'home' : 'home-outline';
            else if (route.name === 'Map') iconName = focused ? 'map' : 'map-outline';
            else if (route.name === 'Camera') iconName = focused ? 'camera' : 'camera-outline';
            else if (route.name === 'Rewards') iconName = focused ? 'gift' : 'gift-outline';
            else if (route.name === 'Profile') iconName = focused ? 'person' : 'person-outline';

            return <Ionicons name={iconName} size={size} color={color} />;
          },
          tabBarActiveTintColor: '#f59e0b',
          tabBarInactiveTintColor: 'gray',
          headerShown: false,
        })}
      >
        <Tab.Screen name="Home" component={HomeStack} />
        <Tab.Screen name="Map" component={MapScreen} />
        <Tab.Screen name="Camera" component={CameraScreen} />
        <Tab.Screen name="Rewards" component={RewardsScreen} />
        <Tab.Screen name="Profile" component={ProfileScreen} />
      </Tab.Navigator>
    </NavigationContainer>
  );
}
