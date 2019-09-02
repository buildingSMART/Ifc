The window profile is represented by a three-dimensional closed curve within a particular shape representation. The profile is used to apply the parameter of the parametric window representation. The following attribute values for the _IfcShapeRepresentation_ holding this geometric representation shall be used:

* _RepresentationIdentifier_ : 'Profile'
* _RepresentationType_ : 'Curve3D', only a single closed curve shall be contained in the set of _IfcShapeRepresentation.Items_.

A 'Profile' representation has to be provided if:

* a parametric representation shall be applied to the window AND
*  
    * the window is 'free standing', or
    * the opening into which the window is inserted is not extruded horizontally (i.e. where the opening profile does not match the window profile) 

The following additional constraints apply to the 'Profile' representation type:

* **Curve**: being an _IfcPolyline_ defining a rectangle.
* **Position**: The curve shall lie in the xz plane of the object placement coordinate (the y coordinate values of the _IfcCartesianPoint_'s shall be 0.).

As shown in Figure 1, the profile defines the outer boundary to which the window lining parameters relate as:

* _IfcWindowLiningProperties.LiningDepth_ starting at distance defined by _LiningOffset_ going into the positive y direction.
* _IfcWindowLiningProperties.LiningThickness_ offset into the inner side of the rectangle.
* _IfcWindowLiningProperties.LiningOffset_ distance along the positive y direction to where the _LiningDepth_ applies.
* _IfcWindowLiningProperties.FirstTransomOffset_ starting at the bottom edge of the rectangle (along local x axis) into the inner side of the rectangle, distance provided as percentage of overall height. Distance to the centre line of the transom. _SecondTransomOffset_ defined accordingly.
* _IfcWindowLiningProperties.FirstMullionOffset_ starting at the left edge of the rectangle (along local z-axis) into the inner side of the rectangle, distance provided as percentage of overall width. Distance to the centre line of the mullion. _SecondMullionOffset_ defined accordingly.

!["standard window"](../../../figures/ifcwindowstandardcase-01.png "Figure 1 &mdash; Window profile")