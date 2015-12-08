
var canvas = document.createElement("canvas");
var ctx = canvas.getContext("2d");
canvas.width = 512;
canvas.height = 480;
document.body.appendChild(canvas);


var lastTime;
function main() {
    var now = Date.now();
    var dt = (now - lastTime) / 1000.0;

    update(dt);
    render();

    lastTime = now;
    requestAnimFrame(main);
};


function init() {
    terrainPattern = ctx.createPattern(resources.get('img/terreno.png'), 'repeat');

    document.getElementById('replay').addEventListener('click', function() {
        reset();
    });

    reset();
    lastTime = Date.now();
    main();
}


resources.load([
    'img/sprites.png',
    'img/terrain.png'
]);
resources.onReady(init);


var player = {
    pos: [0, 0],
    sprite: new Sprite('img/sprites.png', [0, 0], [39, 39], 16, [0, 1])
};

var bullets = [];
var enemies = [];
var explosions = [];

var lastFire = Date.now();
var gameTime = 0;
var isGameOver;
var terrainPattern;


var score = 0;
var scoreEl = document.getElementById('score');

