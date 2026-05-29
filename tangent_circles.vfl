/* context: Attribute Wrangle (run over detail (only once)) */

/* This code is intended in combination with my apollonian gasket code
 * as it prepares everything we'll need */

float radius = chf("radius");
float radius2 = chf("radius2");
float radius3 = radius -radius2;
float angle = $PI*2 * chf("angle");

vector angle_offset = set(cos(angle),sin(angle),0) ;
vector center1 = set(0,0,0);
float center2_x = (radius - radius2)-((radius - radius2)-(angle_offset.x)* (radius-radius2));
float center2_y = (angle_offset.y)* (radius-radius2);
vector center2 = set(center2_x,center2_y,0);
float center3_x = (-radius + radius3)+((radius - radius3)+(-angle_offset.x)* (radius-radius3));
float center3_y = (-angle_offset.y)* (radius-radius3);
vector center3 = set( center3_x,center3_y,0);

vector center_array[] = array(center1,center2,center3);
float radius_array[] = array(radius,radius2,radius3);

float curvature1 = -1.0/radius;
float curvature2 = 1.0/radius2;
float curvature3 = 1.0/radius3;

float curvature_array[] = array(curvature1,curvature2,curvature3);
dict circle0 = set("center",center_array[0],"curvature",curvature_array[0]);
dict circle1 = set("center",center_array[1],"curvature",curvature_array[1]);
dict circle2 = set("center",center_array[2],"curvature",curvature_array[2]);
dict triplet = set("0",circle0,"1",circle1,"2",circle2);
dict queue[];
push(queue,triplet);

setdetailattrib(0,"center_array",center_array);
setdetailattrib(0,"curvature_array",curvature_array);
setdetailattrib(0,"queue",queue);

for(int i = 0; i <= 2; i++){
    vector pos = center_array[i];
    float pscale = radius_array[i];
    int pt = addpoint(0,pos);
    float curvature = curvature_array[i];
    setpointattrib(0,"pscale",pt,pscale);
    setpointattrib(0,"curvature",pt,curvature);
}
