# XSeries
[![Bukkit Version](https://img.shields.io/badge/bukkit-1.16-dark_green.svg)](https://shields.io/)
[![Java](https://img.shields.io/badge/java-8-dark_green.svg)](https://shields.io/)
[![Build Status](https://travis-ci.com/CryptoMorin/XSeries.svg?branch=master)](https://travis-ci.com/CryptoMorin/XSeries)
![maven-central](https://img.shields.io/maven-central/v/com.github.cryptomorin/XSeries)

XSeries is a set of utility classes mainly designed to provide cross-version support for Minecraft Bukkit servers.
But it also includes numerous extra methods to help developers design their plugins easier.
Some utilities are completely unrelated to cross-version support
such as NoteBlockMusic.\
Don't forget to add `api-version: "1.13"` to your `plugin.yml`

This project aims to provide quality utilities with high performance using the latest yet efficient techniques.
Although support for old versions (like 1.8) will still remain for future updates, I highly encourage all server owners
to update your servers to 1.12 if you're using an older version.


### Links

This project was mainly posted in [SpigotMC](https://www.spigotmc.org/threads/378136/)\
Most of the updates and news will be announced there.


### Getting Started

When compiling your plugin you should be using the latest version that your plugin is going to support.\
Which means, at least you have to use 1.13 (for cross-version support utilities only)
You can clone the project using: `git clone https://github.com/CryptoMorin/XSeries.git`

All the methods are explained in the JavaDoc. Please read the JavaDoc before using a method.
It's quite common to miss the whole purpose of cross-version support by using the wrong methods.

You can use the classes individually or use the maven dependency.
Most of the utilities are intended to be independent. However some
utilities such as [XParticle](src/main/java/com/cryptomorin/xseries/XParticle.java) are intended to use
another class ([ParticleDisplay](src/main/java/com/cryptomorin/xseries/ParticleDisplay.java))


#### Maven ![maven-central](https://img.shields.io/maven-central/v/com.github.cryptomorin/XSeries)
```xml
<dependency>
    <groupId>com.github.cryptomorin</groupId>
    <artifactId>XSeries</artifactId>
    <version>version</version>
</dependency>
```

You shouldn't worry if the reflection or other classes are going to use your memory with the heavy useless static cache.
As long as you don't use them anywhere in your code, they won't initialize.

**Note:** DO NOT extract the Jar into your project if you're using maven. You have to shade the library,
otherwise your plugin or other plugins will break due to version mismatch.
To shade the library:
```xml
<plugin>
    <groupId>org.apache.maven.plugins</groupId>
    <artifactId>maven-shade-plugin</artifactId>
    <version>3.2.4</version>
    <configuration>
        <relocations>
            <relocation>
                <pattern>com.cryptomorin.xseries</pattern>
                <!-- Be sure to change the package below -->
                <shadedPattern>my.plugin.utils</shadedPattern>
            </relocation>
        </relocations>
    </configuration>
    <executions>
        <execution>
            <phase>package</phase>
            <goals>
                <goal>shade</goal>
            </goals>
        </execution>
    </executions>
</plugin>
```

### Contributing

There's always room for improvement. If you know better ways of doing things, I really appreciate it if you can share it with me.
But please make sure you know what you're doing and tested the project on different versions.
Any new ideas are welcome as long as it's useful not just for you but for everyone else.\
Please refer to [contributing guidelines](CONTRIBUTING.md) for more info.
