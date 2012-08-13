    var ninja {
      yell: function(n) {
        return n > 0 ? ninja.yell(n-1) + "a" : "hiy";
      }
    };