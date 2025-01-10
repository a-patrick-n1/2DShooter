# 2DShooter

[Try game here](https://a-patrick-n1.github.io/2DShooter/)

### This is a personal project I'm working on, so far I've made:

+ classes for sprites
+ *schmovement* using wasd
+ **shooting** using spacebar
+ enemy sprite
+ animation for updating characters

![idea for game](https://images-wixmp-ed30a86b8c4ca887773594c2.wixmp.com/f/e8d91c7a-24e6-4cc6-a31c-a7c4f08ebb8d/d7zpgtu-b66f7250-e18a-4c51-87f9-065746532c04.png/v1/fit/w_576,h_344,q_70,strp/a_platformer_in_the_forest_by_buch415_d7zpgtu-375w-2x.jpg?token=eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJzdWIiOiJ1cm46YXBwOjdlMGQxODg5ODIyNjQzNzNhNWYwZDQxNWVhMGQyNmUwIiwiaXNzIjoidXJuOmFwcDo3ZTBkMTg4OTgyMjY0MzczYTVmMGQ0MTVlYTBkMjZlMCIsIm9iaiI6W1t7ImhlaWdodCI6Ijw9MzQ0IiwicGF0aCI6IlwvZlwvZThkOTFjN2EtMjRlNi00Y2M2LWEzMWMtYTdjNGYwOGViYjhkXC9kN3pwZ3R1LWI2NmY3MjUwLWUxOGEtNGM1MS04N2Y5LTA2NTc0NjUzMmMwNC5wbmciLCJ3aWR0aCI6Ijw9NTc2In1dXSwiYXVkIjpbInVybjpzZXJ2aWNlOmltYWdlLm9wZXJhdGlvbnMiXX0.rvqO7cZaqE3PPR005QWIuVkm_gBvTpd8w92mBbSn9aM)

My current problem is adding object parameters to add images to the sprites.

``` js
class Sprite {
    constructor({position, color = 'red'}){
        this.position = position
        this.color = color
        this.position = {
            x: this.position.x,
            y: this.position.y
        }
        this.velocity = {
            x: 0,
            y: 0
        }
        this.width = 150
        this.height = 150
        this.sides = {
            bottom: this.position.y + this.height,
            right: this.position.x + this.width
        }
        this.left = false
        this.right = false
        this.shot = false
        this.jumps = 2
    }
    draw() {
        c.fillStyle = this.color
        c.fillRect(this.position.x, this.position.y, this.width, this.height)
    }
    update() {
        this.position.y += this.velocity.y
        this.position.x += this.velocity.x
        this.sides.bottom = this.position.y + this.height
        if(this.sides.bottom >= canvas.height){
            this.velocity.y = 0
            this.position.y = canvas.height - this.height
            this.jumps = 2
        } else {
            this.velocity.y++
        }
    }
}
```
