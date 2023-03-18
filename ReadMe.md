Forked from https://github.com/intel/ARM_NEON_2_x86_SSE.git.

Add the following intinsics accelerating convolution.

Dot product operations (enabled by arch=armv8.2-a+dotprod):
vdot_u32, vdotq_u32, vdot_s32, vdotq_s32, vdot_lane_u32, vdotq_lane_u32, vdot_lane_s32, vdotq_lane_s32, vdot_laneq_u32, vdotq_laneq_u32, vdot_laneq_s32, vdotq_laneq_s32

Dot product operations (enabled arch=armv8.2-a+i8mm):
vusdot_s32, vusdotq_s32, vusdot_lane_s32, vusdotq_lane_s32, vsudot_lane_s32, vsudotq_lane_s32, vusdot_laneq_s32, vusdotq_laneq_s32, vsudot_laneq_s32, vsudotq_laneq_s32

8-bit integer matrix multiply (I8MM) operations (enabled by arch=armv8.2-a+i8mm):
vmmlaq_s32, vmmlaq_u32, vusmmlaq_s32

Floating-point fused multiply-add to accumulator (enabled by fpu=neon-vfpv4):
vfma_f32, vfmaq_f32

Floating-point fused multiply-subtract from accumulator (enabled by fpu=neon-vfpv4):
vfms_f32, vfmsq_f32

*****************************************************************************************
 The NEON_2_SSE.h file is intended to simplify ARM->IA32 porting.
 It makes the correspondence (or a real porting) of ARM NEON intrinsics as defined in "arm_neon.h" header
 and x86 SSE (up to SSE4.2) intrinsic functions as defined in corresponding x86 compilers headers files.
 ****************************************************************************************

To take advantage of this file just include it in your project that uses ARM NEON intinsics instead of "arm_neon.h", compile it as usual and enjoy the result.

For significant performance improvement in some cases you might need to define USE_SSE4 in your project settings. Otherwise SIMD up to SSSE3 to be used.

If NEON2SSE_DISABLE_PERFORMANCE_WARNING macro is defined, then the performance warnings are disabled.

For more information and license please read the NEON_2_SSE.h content.

The unit tests set used for ARM NEON - x86 SSE conformance verification is  https://github.com/christophe-lyon/arm-neon-tests
