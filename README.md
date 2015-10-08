# Planets-Python

#this is a file that allows a user to pick a planet or some other 
#celestial body and then the program askes the user what they like to 
#know about the celestial accoording to displayed options. 

import math

#return the radius for the given planet
def getRadius(radius):
	return radius
#return the diameter for the given planet 
#return the circumference of the given planet 
def getCircumference(radius):
	return 2*radius*math.pi  	
#return the surface area of the given planet 
def getSurfaceArea(radius):
	return 4*math.pi*(radius**2)
#return the mass of the given planet 
def getMass(mass): 	
	return mass
#return the celestial type of the givne planet or moon, etc.
def getType(celestialType):
	return celestialType 
#return the surface area of the planet compared to Earth
def compareSurfaceAreaToEarth(radius, earthSurfaceArea):
	planetSurfaceArea = 4*math.pi*(radius**2)
	return planetSurfaceArea/earthSurfaceArea
def getDiameter(radius):
	return radius*2
	 
#continue looping until user exit
while(True):

	print "Which object would like to know about?"
	userSelectedPlanet = raw_input ()
	#always change string to uppercase for correct comparison 
	userSelectedPlanet = userSelectedPlanet.upper()
	#loop through first to get surface area of Earth 
	for row3 in file('objectInfo.txt', 'r'):

		row4 = row3.split(" ")

		if row4[0] == 'Earth': 

			#storing surfaceArea of Earth to use for comparison
			earthSurfaceArea = (float(row4[2])**2)*math.pi*4 


	#go through rows from file to get information on earth
	for row0 in file('objectInfo.txt', 'r'):
		row1 = row0.split(" ")
		
	#go through rows from file again to get information on user selected 
	#planet
		
			#check userSelectedPlanet against upper case string 
		if (row1[0]).upper() == userSelectedPlanet:
			name = row1[0]
		#change mass and radius strings into floats so can perform
		#calculations
			mass = float(row1[1])
			radius = float(row1[2])
			celestialType = row1[3]
			print 'What would you like to know about?'
			print '(0) Radius'
			print '(1) Diameter'
			print '(2) Circumference'
			print '(3) Mass'
			print '(4) Classification'
			print '(5) Surface Area'
			print '(6) Size compared to Earth (ratio of surface areas)'
			userSelectedTopic = int(raw_input())			
		#checking for the number the user types for selection						
			if userSelectedTopic == 0:
			#changing result of getRadius to a string for concatenation 
				print 'The radius of ' + name + ' is ' + str(getRadius(radius)) + ' km.'
			if userSelectedTopic == 1:
				print 'The diameter of ' + name + ' is ' + str(getDiameter(radius)) + ' km.'
			if userSelectedTopic == 2:
				print 'The circumference of ' + name + ' is ' + str(getCircumference(radius)) + ' km.'
			if userSelectedTopic == 3:
				print 'The mass of ' + name + ' is ' + str(getMass(mass)) + ' Earth masses.'
			if userSelectedTopic == 4:
				classification = getType(celestialType)
			#checking to see if use a or an from next vowel 
				if classification[0] == 'a' or classification[0] == 'e' or classification[0] == 'i' or classification[0] == 'o' or classification[0] == 'u': 
					print 'The classification of ' + name + ' is an ' + classification
				else:
					print 'The classification of ' + name + ' is a ' + classification
			if userSelectedTopic == 5:
				print 'The surface area of ' + name + ' is ' + str(getSurfaceArea(radius)) + ' km squared.'
			if userSelectedTopic == 6:
				print name + ' is ' + str(compareSurfaceAreaToEarth(radius, earthSurfaceArea)) + ' times larger than Earth.'

