# Actor.h

#ifndef ACTOR_H_
#define ACTOR_H_

#include "GraphObject.h"
class Actor : public GraphObject
{
public:
	Actor(int imageID, int startX, int startY, Direction dir, double size, unsigned int depth);
	virtual ~Actor();
	virtual void doSomething() = 0;
	virtual void getAnnoyed() = 0;
};
// Students:  Add code to this file, Actor.cpp, StudentWorld.h, and StudentWorld.cpp

#endif // ACTOR_H_


#ifndef DIRT_H_
#define DIRT_H_

#include "Actor.h"
class Dirt : public Actor
{
public:
	Dirt(int imageID, int startX, int startY, Direction dir, double size, unsigned int depth);
	virtual ~Dirt();
};

#endif // DIRT_H_


#ifndef PERSON_H_
#define PERSON_H_

#include "Actor.h"
class Person : public Actor
{
public:
	Person(int imageID, int startX, int startY, Direction dir, double size, unsigned int depth);
	virtual ~Person();
	int health();
private:
	int m_health;
};
#endif PERSON_H_


#ifndef FRACKMAN_H_
#define FRACKMAN_H_

#include "Actor.h"
class Frackman : public Person
{
public:
	Frackman(int imageID, int startX, int startY, Direction dir, double size, unsigned int depth, int health);
	virtual ~Frackman();
	virtual void doSomething();
	virtual void getAnnoyed();
};
#endif PERSON_H_
