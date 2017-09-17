# Classes
[iframe](https://framer.cloud/nxqci/)(https://framer.cloud/nxqci/)

<iframe src="https://framer.cloud/nxqci/"><iframe>

# Basic Construction

    superman = 
    	name: "Clark"
    	realName: "Kal-El"
    	powers: ["Strength, Speed, Flight"]
    	strength: 9001
    	punchBatman: ->
    		batman.health -= this.strength
    
    batman = 
    	name: "Bruce"
    	health: 5000
    	powers: ["Detective", "Tough", "GAdgets"]
    	deployKrypto: ->
    		superman.strength = superman.strength * 0.1
    		
    batman.deployKrypto()
    superman.punchBatman()
    
    print batman.health

Klassendeklaration

    class SuperHero
    #Eigenschaften : Properties
    	secretIdentity
    	strength
    	health
    # Fähigkeiten
    	attack(target)

Aufruf constructor Function

    class SuperHero
    	constructor: (options)->
    			
    		secretIdentity
    		strength
    		health
    		attack(target)

    class SuperHero
    	constructor: (options)->
    		#Erzeugt eine Instanz des Obejekts Superhero
    		this.secretIdentity
    
    		strength
    		health
    		attack(target)
    		

Defining Properties of the Object

    class SuperHero
    	constructor: (options)->
    			
    		this.secretIdentity = options.name
    		this.strength = options.strength
    		this.health = options.health
    		attack(target)
    		

default Values

    class SuperHero
    	constructor: (options)->
    		# Wenn nicht vorhanden dann default Value
    		this.secretIdentity = options.name || "Unknown"
    		this.strength = options.strength || 1000
    		this.health = options.health || 5000
    		attack(target)

Adding Function

    class SuperHero
    	constructor: (options)->
    			
    		this.secretIdentity = options.name || "Unknown"
    		this.strength = options.strength || 1000
    		this.health = options.health || 5000
    		
    	attack: (target) ->
    		target.health -= this.strength

Erweiterung der Klasse SuperHero

    class Batman extends SuperHero
    	constructor: (options) ->
    		super (options)
    	deployKrypto: () ->
    		superman.strength = superman.strength * 0.1

---

    class Button extends Layer
    	constructor: (options) ->
    		options.width ?= 60
    		options.height ?= 60
    		options.backgroundColor ?= "#a3b"
    		super(options)
    
    		this.center()
    		
    		this.states =
    			on:
    				borderRadius: 50
    		this.onTap ->
    			this.stateCycle()
    
    button = new Button
    	shadowX: 20
    	backgroundColor:"red"

---

    class Ghost extends Layer
    	constructor: (options)->
    		options.width ?= 100
    		super(options)
    		@opacity = 0.9
    # 		@width ?= 300
    		
    c = new Ghost
    	width: 10
    	height: 700

    class ToggleButton extends Framer.Layer
    	constructor:(config={})->
    		config.width ?= 60
    		super(config)
    		@backgroundColor = "red"
    		@states.default.animationOptions = {time:0.25}
    		@states.clicked =
    			backgroundColor: "limeGreen"
    			borderWidth:25
    			animationOptions:{time:0.25}
    		@onMouseDown ->
    			@states.next() 
    
    bg = new Layer
    	size:Screen.size
    	backgroundColor: "white"
    	
    	
    b1 = new ToggleButton
    	width: 120	
    b2 = new ToggleButton
    	x:201
    b3 = new ToggleButton
    	y:201

[](https://gist.github.com/helloMikkie/56759fd9f5795524beb553653dc13ace)
