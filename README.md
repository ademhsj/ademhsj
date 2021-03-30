// ==UserScript==
// @name Bot nhb ِA
// @version 0.1
// @description a- b -c
// @author طناف
// @match https://*.tribalwars.ae/game.php?*=am_farm*
// @grant none
// ==/UserScript==
/*
A = 8
B = 9
C = 10
*/
var type = 8;
var speed = 20000;
setInterval(
function(){
$('#plunder_list tr:eq(1) td:eq('+ type +') a').click();
$('#plunder_list tr:eq(1)').remove();
},Math.ceil( (Math.random() * 500 ) + 500));
setTimeout(
function(){
if ( $('#village_switch_right').length == 0){
location.reload();
}else{
location.href = $('#village_switch_right').attr('href');
}
}, speed);


$(function (){
$('.row_a, .row_b').each(function() {
if ( $(this).find('td:eq(3)').html().match(/command\/attack\.png/) ){
$(this).remove();
}
});
});

$(function (){
$("a.farm_icon_a, a.farm_icon_b, a.farm_icon_c").click(function() {
$(this).parent().parent().remove();
});
});

$(function (){
$('.row_a, .row_b').each(function() {
if ( $(this).find('td:eq(10)').html().match(/farm_icon_disabled/) && $(this).find('td:eq(11)').html().match(/farm_icon_disabled/) && $(this).find('td:eq(12)').html().match(/farm_icon_disabled/)){
$(this).remove();
}
});
});

$(function (){
$('.row_a, .row_b').each(function() {
if ( $(this).find('td:eq(1)').html().match(/green/) ){
$(this).find('td:eq(8),td:eq(9),td:eq(10)').css('background-color', 'green');
}
else if ( $(this).find('td:eq(1)').html().match(/yellow/) ){
$(this).find('td:eq(8),td:eq(9),td:eq(10)').css('background-color', 'yellow');
}
else if ( $(this).find('td:eq(1)').html().match(/blue/) ){
if ( $(this).find('td:eq(1)').html().match(/red_blue/) ){
$(this).find('td:eq(8),td:eq(9),td:eq(10)').css('background-color', '#660066');
}
else{
$(this).find('td:eq(8),td:eq(9),td:eq(10)').css('background-color', 'blue');
}
}
});
});

void(0);
