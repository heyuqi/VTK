set(TerrainPolylineEditor_ARGS -ProjectionMode 2 -HeightOffset 100)
vtk_add_test_cxx(
  BoxWidget2.cxx
  BoxWidget.cxx
  ImagePlaneWidget.cxx
  TerrainPolylineEditor.cxx
  TestAffineWidget.cxx
  TestAngleWidget2D.cxx
  TestAngleWidget3D.cxx
  TestBalloonWidget.cxx
  TestBiDimensionalWidget.cxx
  TestBorderWidget.cxx
  TestBrokenLineWidget.cxx
  TestButtonWidget.cxx
  TestCameraWidget.cxx
  TestCellCentersPointPlacer.cxx
  TestCenteredSliderWidget2D.cxx
  TestCheckerboardWidget.cxx
  TestConstrainedHandleWidget.cxx
  TestContourWidget2.cxx
  TestDijkstraImageGeodesicPath.cxx
  TestDistanceWidget3D.cxx
  TestDistanceWidget.cxx
  TestFixedSizeHandleRepresentation3D.cxx
  TestFocalPlaneContour.cxx
  TestHandleWidget2D.cxx
  TestHandleWidget.cxx
  TestImageActorContourWidget.cxx
  TestImageCroppingRegionsWidget.cxx
  TestImageTracerWidget.cxx
  TestImplicitPlaneWidget2b.cxx
  TestImplicitPlaneWidget2.cxx
  TestImplicitPlaneWidget2LockNormalToCamera.cxx
  TestImplicitPlaneWidget.cxx
  TestLogoWidgetAlphaBlending.cxx
  TestLogoWidget.cxx
  TestLogoWidgetDepthPeeling.cxx
  TestOrientationMarkerWidget.cxx
  TestOrthoPlanes.cxx
  TestParallelopipedWidget.cxx
  TestPickingManagerSeedWidget.cxx
  TestPlaybackWidget.cxx
  TestPointHandleRepresentation3D.cxx
  TestProgrammaticPlacement.cxx
  TestProp3DButtonRepresentation.cxx,NO_VALID
  TestRectilinearWipeWidget.cxx
  TestResliceCursorWidget2.cxx
  TestResliceCursorWidget3.cxx
  TestScalarBarWidget.cxx
  TestSeedWidget2.cxx
  TestSeedWidget.cxx
  TestSeedWidgetNonUniformRepresentations.cxx
  TestSliderWidget2D.cxx
  TestSliderWidget.cxx
  TestSplineWidget.cxx
  TestSphereWidgetZoomInOut.cxx
  TestTextWidget.cxx
  )
vtk_add_test_cxx(NO_VALID
  vtkAngleRepresentation2DTest1.cxx
  vtkAngleRepresentation3DTest1.cxx
  vtkAngleWidgetTest1.cxx
  vtkBalloonRepresentationTest1.cxx
  vtkBalloonWidgetTest1.cxx
  vtkBiDimensionalRepresentation2DTest1.cxx
  vtkBiDimensionalWidgetTest1.cxx
  vtkBorderWidgetTest1.cxx
  vtkCaptionRepresentationTest1.cxx
  vtkCaptionWidgetTest1.cxx
  vtkConstrainedPointHandleRepresentationTest1.cxx
  vtkHoverWidgetTest1.cxx
  vtkLineRepresentationTest1.cxx
  vtkLineWidget2Test1.cxx
  vtkSeedRepresentationTest1.cxx
  vtkSeedWidgetTest1.cxx
  vtkSplineWidget2Test1.cxx
  vtkTextRepresentationTest1.cxx
  vtkTextWidgetTest1.cxx
  )

# Tests with data
vtk_add_test_cxx(
  TestDijkstraGraphGeodesicPath.cxx
  TestLineWidget2.cxx
  TestLineWidget.cxx
  TestPlaneWidget.cxx
  TestPointWidget.cxx
  TestPolygonalHandleRepresentations.cxx
  TestPolygonalRepresentationHandleWidget.cxx
  TestPolygonalSurfaceConstrainedDistanceWidget.cxx
  TestPolyPlane.cxx,NO_VALID
  TestSphereHandleWidget.cxx
  TestSurfaceConstrainedHandleWidget.cxx
  TestTensorProbeWidget.cxx
  )

if(NOT VTK_OPENGL_HAS_OSMESA)
  vtk_add_test_cxx(TestPickingManagerWidgets.cxx)
endif()

vtk_test_cxx_executable(${vtk-module}CxxTests RENDERING_FACTORY)

set_tests_properties(${vtk-module}Cxx-TerrainPolylineEditor
  PROPERTIES TIMEOUT 90)

if(NOT VTK_OPENGL_HAS_OSMESA)
  set_tests_properties(${vtk-module}Cxx-TestPickingManagerSeedWidget
    PROPERTIES TIMEOUT 60)
endif()
