oBDSC = InheritO(oPotatoMine, {
    EName: "oBDSC",
    CName: "冰冻生菜",
    SunNum: 0,
    coolTime: 15,
    CanGrow: function(c, b, e) {
        var a = b + "_" + e,
        d = oS.ArP;
        return d ? oGd.$LF[b] == 1 ? (e > 0 && e < d.ArC[1] && !(oGd.$Crater[a] || oGd.$Tombstones[a] || c[1])) : c[0] && !c[1] : oGd.$LF[b] == 1 ? !(e < 1 || e > 9 || oGd.$Crater[a] || oGd.$Tombstones[a] || c[1]) : c[0] && !c[1]
    },
    Tooltip: "敌人接触后冰冻他",
    Produce: '可以永久冰冻敌人',
    canTrigger: 0,
    PrivateBirth: function(b, a) { ! a && oSym.addTask(0,
        function(d) {
            var c = $P[d];
            c && ($(d).childNodes[1].src = "images/Plants/PotatoMine/PotatoMine.gif", c.Status = 1, c.canTrigger = 1, c.getHurt = c.getHurt2)
        },
        [b.id])
    },
    NormalAttack: function(j, h, e) {
        var g = this,
        b = g.id,
        d = $(b),
        c = oZ.getArZ(j, h, e),
        f = c.length,
        a;
        while (f--) { (a = c[f]).Altitude < 2 && a.getBDSCFreeze()
        }
        g.Die(1);
        PlayAudio("potato_mine");
        EditEle(d.childNodes[1], {
            src: "images/Plants/PotatoMine/PotatoMine_mashed.gif"
        },
        {
            width: "132px",
            height: "93px",
            left: "-40px",
            top: "-20px"
        });
        NewImg(0, "images/Plants/PotatoMine/ExplosionSpudow.gif", "left:-90px;top:-40px", d);
        oSym.addTask(200,
        function(i) {
            ClearChild(i.lastChild);
            oSym.addTask(100, ClearChild, [i])
        },
        [d])
    }
}),
oHJBL = InheritO(CPlants, {
    EName: "oHJBL",
    CName: "黄金蓓蕾",
    width: 75,
    height: 55,
    beAttackedPointR: 55,
    SunNum: 0,
    coolTime: 180,
    Tooltip: "生产1000阳光",
    PicArr: ["images/Card/Plants/PotatoMine.png", "images/Plants/PotatoMine/PotatoMine.gif", "images/Plants/PotatoMine/PotatoMine.gif", "images/Plants/PotatoMine/PotatoMineNotReady.gif", "images/Plants/PotatoMine/PotatoMine_mashed.gif", "images/Plants/PotatoMine/ExplosionSpudow.gif"],
    Produce: '生产1000阳光后什么也不做的黄金蓓蕾',
    Produce1000Sun: function(a, c, b) {
        AppearSun(Math.floor(c + Math.random() * 41), b,1000, 0)
    },
    PrivateBirth: function() {
       this.Produce1000Sun()
    }
})
