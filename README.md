Cocos2dHTML5 Box2D JS
=====

Box2d changed to support debug draw for Cocos2d HTML5 v2.2

The file: box2d.js is the library and the Box2dTestJS.js has the example.

For implement add the next code:

In the ctor function use:

        var debugDraw = new b2DebugDraw();
        debugDraw.SetSprite(cc.drawingUtil);
        debugDraw.SetDrawScale(PTM_RATIO);
        debugDraw.SetFillAlpha(0.8);
        debugDraw.SetLineThickness(1.0);
        debugDraw.SetFlags(b2DebugDraw.e_shapeBit | b2DebugDraw.e_jointBit/* | b2DebugDraw.e_centerOfMassBit*/);
        this.world.SetDebugDraw(debugDraw);

And in the draw method use:

    draw:function () {
        this.world.DrawDebugData();
        this._super();
    }
    
And Box2d draw the debug data.

The circle method no support drawSolidCircle if someone can implement this feature I feel happy =D
