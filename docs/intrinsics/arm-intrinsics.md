﻿---
title: ARM 내장 함수
ms.date: 09/02/2019
f1_keywords:
- arm_neon/vsetq_lane_p8
- armintr/_arm_uxtb
- arm_neon/vld4_lane_p8
- arm_neon/vrshrn_n_s64
- arm_neon/vsli_n_u32
- arm_neon/vsraq_n_u16
- arm_neon/vcgt_f32
- armintr/__iso_volatile_store32
- arm_neon/vceqq_f32
- armintr/_arm_smlal
- arm_neon/vmull_n_s32
- arm_neon/vmax_s8
- arm_neon/vmvn_u32
- arm_neon/vrshl_u32
- arm_neon/int32x2_t
- arm_neon/vdupq_n_p8
- arm_neon/vpmax_u16
- arm_neon/vtrnq_s32
- arm_neon/vset_lane_f32
- arm_neon/vrev64_s8
- arm_neon/vtrnq_p8
- arm_neon/vqshlq_u64
- arm_neon/vld1q_dup_s64
- arm_neon/vmovq_n_u64
- arm_neon/vqshrn_n_u16
- arm_neon/vhadd_s32
- arm_neon/vrhaddq_u32
- arm_neon/vst1q_p8
- arm_neon/vshrn_n_s16
- arm_neon/vget_high_f32
- arm_neon/vuzpq_s16
- arm_neon/vand_u16
- arm_neon/vmulq_s32
- arm_neon/vrsraq_n_s64
- arm_neon/vceqq_s8
- arm_neon/uint64x1x3_t
- arm_neon/veor_u32
- armintr/_arm_pkhtb
- arm_neon/vorrq_u16
- arm_neon/vpaddl_s8
- arm_neon/vmla_n_s16
- arm_neon/vqdmlal_lane_s32
- arm_neon/vshlq_n_u8
- arm_neon/vst2_lane_p8
- arm_neon/vld3q_u16
- arm_neon/vandq_u8
- arm_neon/vst1_u64
- arm_neon/vaddq_s64
- arm_neon/vuzpq_u32
- arm_neon/vld3_lane_p8
- arm_neon/vminq_s32
- arm_neon/vabd_u16
- arm_neon/vdup_n_u32
- arm_neon/vmul_p8
- arm_neon/vsra_n_u16
- arm_neon/vst3q_u16
- arm_neon/int32x2x3_t
- arm_neon/vld2_dup_u16
- arm_neon/vrhaddq_u8
- arm_neon/vhadd_u8
- arm_neon/vgetq_lane_s32
- arm_neon/vcleq_u16
- arm_neon/vabdq_s8
- arm_neon/vrev16q_u8
- arm_neon/vqshlu_n_s64
- arm_neon/vcvt_n_s32_f32
- arm_neon/vqrshrn_n_s64
- arm_neon/vst1q_p16
- arm_neon/vgetq_lane_s16
- arm_neon/vtstq_u32
- arm_neon/vmlsl_n_s16
- arm_neon/vcge_s8
- arm_neon/vshr_n_s16
- armintr/_arm_rbit
- arm_neon/vmls_u32
- arm_neon/vmls_lane_u32
- arm_neon/vcvtq_n_s32_f32
- arm_neon/vqshl_n_s8
- arm_neon/vst1q_s16
- armintr/__emit
- arm_neon/vshlq_s64
- arm_neon/vuzp_s8
- arm_neon/vld1q_lane_s64
- arm_neon/veorq_s32
- arm_neon/vaddq_u64
- arm_neon/vceq_s32
- arm_neon/vmovn_u16
- arm_neon/vabal_s8
- arm_neon/vabsq_f32
- armintr/_arm_smuad
- arm_neon/veor_u8
- arm_neon/int16x4_t
- arm_neon/vsraq_n_s16
- arm_neon/vshlq_s8
- arm_neon/vcreate_u32
- arm_neon/vzipq_s8
- arm_neon/vst3q_u8
- arm_neon/int64x1x4_t
- armintr/__iso_volatile_store16
- arm_neon/vst4_lane_p16
- arm_neon/vld1_dup_p16
- arm_neon/vhadd_s16
- arm_neon/vtbl2_s8
- arm_neon/veorq_u32
- arm_neon/vqdmlal_lane_s16
- arm_neon/vrsra_n_u8
- arm_neon/vbslq_u16
- arm_neon/vget_low_s64
- arm_neon/vceq_u16
- arm_neon/vdupq_lane_u32
- arm_neon/vabdl_u32
- arm_neon/vmlal_s32
- arm_neon/vst1_lane_u8
- arm_neon/vld4q_f16
- arm_neon/vqdmlsl_s32
- arm_neon/vqrdmulh_s32
- arm_neon/vqrshl_u8
- arm_neon/uint32x4x4_t
- arm_neon/vabaq_u16
- arm_neon/vcnt_p8
- arm_neon/vld3q_s16
- arm_neon/vshl_n_u32
- arm_neon/vrev64q_u16
- arm_neon/vextq_s64
- arm_neon/vhsubq_s8
- arm_neon/vld2_dup_u8
- arm_neon/vst3_s16
- arm_neon/vorn_u16
- arm_neon/vst4_f16
- arm_neon/vpadalq_u8
- armintr/__iso_volatile_load8
- arm_neon/vmovl_u16
- arm_neon/vld4q_u32
- arm_neon/vcgt_u32
- arm_neon/vmlaq_n_u32
- arm_neon/vrsra_n_u64
- arm_neon/vst4_s8
- arm_neon/vcvtq_n_f32_u32
- arm_neon/vst2q_u16
- arm_neon/vqshrn_n_s16
- arm_neon/vld4_s16
- arm_neon/uint16x8x4_t
- arm_neon/vrsqrte_u32
- arm_neon/vcltq_s8
- arm_neon/vst3_u16
- arm_neon/vst2_f32
- arm_neon/vld2_u64
- arm_neon/vst1_u16
- arm_neon/vmls_s16
- arm_neon/vqrshlq_s32
- arm_neon/vqdmull_s16
- arm_neon/vld2_lane_p16
- arm_neon/vpaddlq_u8
- arm_neon/vcvt_n_f32_u32
- arm_neon/vcgtq_u8
- arm_neon/vshl_s32
- arm_neon/vtbx3_p8
- arm_neon/vld3_dup_s32
- arm_neon/int16x4x3_t
- arm_neon/vcale_f32
- arm_neon/vqabsq_s32
- arm_neon/vmulq_u16
- arm_neon/vst1_s8
- arm_neon/vclt_u8
- armintr/_arm_sxtb16
- arm_neon/vshr_n_s8
- arm_neon/vst1_lane_f16
- arm_neon/vorn_s64
- armintr/_arm_usub8
- arm_neon/vst4_lane_f32
- arm_neon/vmls_lane_u16
- arm_neon/vpaddl_u32
- arm_neon/vdup_lane_u64
- arm_neon/vsri_n_p16
- arm_neon/vqrshlq_u64
- arm_neon/vclz_s16
- arm_neon/vsra_n_u32
- arm_neon/vabaq_s8
- arm_neon/vst2_lane_s8
- arm_neon/vcvt_n_u32_f32
- arm_neon/vst3_u32
- arm_neon/vcvtq_f32_u32
- arm_neon/vraddhn_s64
- armintr/_arm_uqsax
- arm_neon/vshl_u8
- armintr/_arm_uqadd16
- arm_neon/vrsra_n_u16
- arm_neon/vrshl_u64
- arm_neon/int32x4x3_t
- arm_neon/vmull_u8
- arm_neon/vcombine_u64
- arm_neon/vmull_u16
- arm_neon/vld1_dup_s8
- armintr/_CountLeadingSigns64
- arm_neon/vqshlq_n_s32
- arm_neon/vrecpe_f32
- arm_neon/vsri_n_u32
- arm_neon/vrsraq_n_s8
- arm_neon/vsetq_lane_s16
- arm_neon/vget_high_u32
- arm_neon/vmlal_u32
- arm_neon/vdupq_lane_s16
- arm_neon/vsubq_u64
- arm_neon/vext_p8
- arm_neon/vshl_u16
- arm_neon/vmls_n_u16
- arm_neon/vmull_s16
- arm_neon/vmovq_n_s64
- arm_neon/vaddq_f32
- arm_neon/vshl_n_s16
- arm_neon/vext_p16
- arm_neon/vextq_u32
- arm_neon/vld1_p8
- arm_neon/veor_s32
- arm_neon/int16x8x4_t
- arm_neon/vst1q_u16
- arm_neon/vzipq_p8
- arm_neon/int32x4x4_t
- arm_neon/vqdmulhq_lane_s32
- arm_neon/vst3_lane_u32
- arm_neon/vhsubq_s32
- armintr/__static_assert
- arm_neon/vst3q_lane_u16
- arm_neon/vpmin_u32
- arm_neon/vrev64q_p16
- arm_neon/vcleq_f32
- arm_neon/vhsub_u16
- arm_neon/vld2_lane_s32
- arm_neon/vmlsl_s32
- armintr/_arm_rev
- arm_neon/vcgeq_s16
- arm_neon/vmulq_s8
- arm_neon/vsri_n_s8
- arm_neon/vpadd_f32
- arm_neon/vld1q_lane_f16
- arm_neon/vmls_u16
- arm_neon/vld1_lane_f32
- arm_neon/vmlaq_lane_s16
- arm_neon/vqadd_u32
- arm_neon/vmul_n_s32
- arm_neon/vld1q_dup_p8
- arm_neon/vtrnq_s8
- arm_neon/vbslq_p8
- arm_neon/vget_lane_s8
- arm_neon/vext_u16
- arm_neon/vsubq_s16
- arm_neon/vld4_lane_s8
- arm_neon/uint32x2x2_t
- arm_neon/vdup_n_s8
- arm_neon/vld4_lane_u16
- arm_neon/vmovq_n_s16
- arm_neon/vst4q_s32
- arm_neon/vst2q_f16
- arm_neon/vbslq_s16
- arm_neon/vand_u64
- arm_neon/poly16_t
- arm_neon/vaba_u16
- arm_neon/vqshlq_s64
- armintr/_arm_uxth
- arm_neon/vst2_lane_s16
- arm_neon/vand_u8
- arm_neon/int8x16x3_t
- arm_neon/vrev64_u16
- arm_neon/vld2_lane_s16
- arm_neon/vabaq_s16
- arm_neon/vsli_n_u8
- arm_neon/vsraq_n_u64
- arm_neon/vmlsl_s16
- arm_neon/vmovn_u64
- arm_neon/vld4_f32
- arm_neon/vst2q_f32
- arm_neon/vtbx3_u8
- arm_neon/vcombine_s8
- arm_neon/vqdmulhq_s32
- arm_neon/vgetq_lane_p8
- armintr/_arm_smusd
- arm_neon/vpmax_u32
- arm_neon/vceq_f32
- arm_neon/vsri_n_p8
- arm_neon/vhsubq_u8
- arm_neon/vuzp_s16
- arm_neon/uint32x2x4_t
- arm_neon/vst4_lane_s32
- arm_neon/vsli_n_p8
- arm_neon/vld3_lane_f16
- arm_neon/vbic_u64
- arm_neon/vmlal_u16
- arm_neon/vmvn_s8
- arm_neon/vtstq_s8
- arm_neon/vmaxq_s32
- arm_neon/vqmovn_u64
- armintr/_arm_ssax
- arm_neon/vext_u32
- arm_neon/vld1_dup_u64
- arm_neon/vmlal_n_s16
- armintr/_arm_smulbb
- arm_neon/vqrdmulhq_lane_s16
- arm_neon/vdup_n_p8
- arm_neon/vaba_s8
- arm_neon/vrshrq_n_s32
- arm_neon/vmvnq_s32
- arm_neon/vpadal_s32
- arm_neon/vqshl_s16
- arm_neon/vtrn_p8
- arm_neon/vzip_s16
- arm_neon/vcge_f32
- armintr/_arm_sxtab16
- arm_neon/vst1q_lane_u64
- arm_neon/vqrshlq_u16
- arm_neon/int8x8_t
- arm_neon/vorr_u8
- arm_neon/vrev64_f32
- arm_neon/vpaddlq_s16
- arm_neon/vdupq_lane_u64
- arm_neon/vcltq_u16
- arm_neon/vst3_lane_f32
- arm_neon/vld2_dup_f32
- armintr/_arm_smmul
- arm_neon/vbsl_s16
- arm_neon/vld1_lane_u8
- arm_neon/vld2q_lane_u16
- arm_neon/vqshlu_n_s32
- armintr/_arm_smlalbt
- arm_neon/vmla_s8
- arm_neon/vsli_n_p16
- arm_neon/vmla_u8
- arm_neon/vqaddq_s16
- arm_neon/vld3_p16
- arm_neon/uint64x2x4_t
- arm_neon/vcnt_u8
- arm_neon/vcltq_u8
- arm_neon/vtbx1_p8
- arm_neon/vrev32q_u16
- arm_neon/vld1_lane_u16
- arm_neon/vqadd_s16
- arm_neon/vcnt_s8
- armintr/_MulUnsignedHigh
- arm_neon/vsliq_n_u8
- arm_neon/vpmin_s16
- armintr/__iso_volatile_load16
- arm_neon/vst2_lane_f32
- arm_neon/vqsubq_s32
- arm_neon/vqshl_s32
- arm_neon/vsraq_n_u32
- arm_neon/vcreate_s32
- arm_neon/vld3q_lane_u32
- arm_neon/vaddq_u16
- arm_neon/vand_s32
- arm_neon/vbicq_s32
- armintr/_arm_smulbt
- arm_neon/vrsra_n_s8
- arm_neon/vshrq_n_u32
- arm_neon/vld4_f16
- arm_neon/vcagtq_f32
- arm_neon/vaddw_u32
- armintr/_arm_uxtah
- arm_neon/vtstq_u8
- arm_neon/vld1_dup_u16
- arm_neon/int16x4x4_t
- arm_neon/vqshluq_n_s8
- arm_neon/vqdmulhq_n_s32
- arm_neon/vst1_s64
- arm_neon/vrsubhn_u16
- arm_neon/vld4_dup_p16
- arm_neon/vmlaq_s32
- arm_neon/vnegq_s32
- arm_neon/vst2q_u8
- arm_neon/vget_low_s32
- arm_neon/vorn_u32
- arm_neon/vld1q_s8
- arm_neon/vandq_s64
- arm_neon/vmvn_p8
- arm_neon/vabdl_s16
- arm_neon/vqshl_u32
- arm_neon/vld3_dup_u16
- arm_neon/vmov_n_f32
- arm_neon/vcvt_f32_u32
- arm_neon/vrhadd_s8
- arm_neon/vpadal_u32
- armintr/_arm_ubfx
- arm_neon/vcgt_s8
- arm_neon/vget_lane_f32
- arm_neon/vcge_s16
- arm_neon/vmov_n_s64
- arm_neon/vmulq_n_f32
- arm_neon/vpadalq_u32
- armintr/_arm_smlaldx
- arm_neon/vtst_u16
- arm_neon/vmls_n_s16
- arm_neon/vcombine_f32
- arm_neon/vld1q_p16
- armintr/_arm_ssat
- arm_neon/vextq_s8
- arm_neon/vmax_u32
- arm_neon/vqsubq_s64
- arm_neon/vcltq_s16
- arm_neon/vst2q_s8
- arm_neon/vpmax_u8
- arm_neon/vld4_dup_p8
- arm_neon/vrshr_n_u64
- arm_neon/vqrshrun_n_s16
- arm_neon/vget_low_u64
- arm_neon/vst2q_s32
- arm_neon/vst4_s32
- arm_neon/vrshrq_n_u8
- arm_neon/vdupq_n_u64
- arm_neon/vsriq_n_u8
- arm_neon/vdupq_lane_u8
- arm_neon/vsriq_n_s64
- arm_neon/vget_low_u8
- arm_neon/vst1_lane_p16
- arm_neon/vld1q_lane_u8
- arm_neon/vcgt_s32
- arm_neon/vst1_lane_u32
- arm_neon/vzipq_p16
- arm_neon/vmvn_u16
- arm_neon/vld1q_lane_u16
- armintr/_MoveToCoprocessor64
- arm_neon/vdup_n_u16
- arm_neon/vzipq_f32
- arm_neon/vshl_s16
- arm_neon/vmlaq_n_s16
- arm_neon/vget_lane_s64
- arm_neon/vld1q_lane_f32
- arm_neon/vnegq_s16
- armintr/_arm_usax
- arm_neon/vabd_s16
- arm_neon/vmovq_n_u32
- arm_neon/vshlq_n_u16
- armintr/_CountLeadingSigns
- arm_neon/vld3q_f16
- arm_neon/vceqq_u32
- arm_neon/int8x8x2_t
- arm_neon/vst2_s64
- arm_neon/vst4q_lane_s16
- arm_neon/vorn_s32
- arm_neon/vcle_f32
- arm_neon/vld1_p16
- arm_neon/vtrn_u32
- arm_neon/vbsl_s32
- arm_neon/float32x2_t
- arm_neon/vmvn_s32
- arm_neon/vqdmlsl_lane_s16
- arm_neon/vtbl3_s8
- arm_neon/vsra_n_u8
- arm_neon/vcvtq_u32_f32
- arm_neon/vst1_p8
- arm_neon/vrev64_p16
- armintr/__ldrexd
- arm_neon/vcgeq_u8
- arm_neon/vmlal_n_s32
- arm_neon/vst1q_lane_p8
- arm_neon/vpadalq_s32
- arm_neon/vtstq_p8
- arm_neon/vld4_lane_u8
- armintr/_arm_ssub16
- arm_neon/vpaddlq_u16
- armintr/_arm_udiv
- arm_neon/vld1_lane_p8
- arm_neon/vst1q_u32
- arm_neon/vld1_f32
- arm_neon/uint64x2x2_t
- arm_neon/vqsubq_u64
- arm_neon/vld4q_s32
- arm_neon/vceq_s16
- arm_neon/vst3_s64
- arm_neon/vext_s8
- armintr/_arm_smlsd
- arm_neon/vpadal_s16
- arm_neon/vbic_s32
- arm_neon/vld1_dup_u8
- arm_neon/vclt_f32
- arm_neon/vrev64_s16
- arm_neon/vrshlq_s64
- arm_neon/vdupq_n_s64
- arm_neon/vuzp_p16
- arm_neon/vld3_dup_p16
- arm_neon/vcreate_s8
- armintr/_arm_smlatt
- arm_neon/vtst_s32
- arm_neon/vshrq_n_s64
- arm_neon/vqshlq_n_s64
- arm_neon/vqshlu_n_s16
- arm_neon/vcleq_s16
- arm_neon/vmull_lane_s16
- arm_neon/int32x4_t
- arm_neon/vqadd_s8
- arm_neon/vld2q_f16
- arm_neon/vld2q_lane_p16
- arm_neon/vadd_u32
- arm_neon/vcntq_u8
- arm_neon/vst1_f32
- arm_neon/vmaxq_u32
- arm_neon/vsub_u64
- arm_neon/vsubl_s32
- arm_neon/poly16x4_t
- arm_neon/vgetq_lane_u16
- arm_neon/vdup_lane_s32
- arm_neon/vrhadd_s32
- arm_neon/veorq_u8
- arm_neon/vclzq_s8
- arm_neon/vsliq_n_s64
- arm_neon/vpadalq_s16
- arm_neon/vmla_n_f32
- arm_neon/vcgt_u16
- armintr/_arm_usada8
- arm_neon/vabd_u32
- arm_neon/vgetq_lane_s8
- arm_neon/vqshlq_n_u64
- arm_neon/vabaq_u32
- armintr/_arm_uhsax
- arm_neon/vmulq_f32
- arm_neon/vld3_dup_s16
- arm_neon/vst3_f16
- arm_neon/vrshrq_n_s64
- armintr/__rdpmccntr64
- arm_neon/vclsq_s32
- arm_neon/vmax_u16
- arm_neon/vmvnq_p8
- arm_neon/veor_u16
- arm_neon/vqshrn_n_u32
- arm_neon/vextq_u64
- arm_neon/vld1q_f32
- arm_neon/vget_low_u32
- arm_neon/vhaddq_s32
- arm_neon/vminq_u16
- arm_neon/vqrdmulhq_lane_s32
- arm_neon/vmla_s16
- arm_neon/vadd_s16
- arm_neon/vbsl_u16
- arm_neon/vhsub_s8
- arm_neon/vld4q_lane_p16
- arm_neon/vld1_s16
- arm_neon/vst2q_lane_p16
- arm_neon/vld2_dup_s8
- arm_neon/vst3q_s16
- arm_neon/vcgeq_u32
- arm_neon/vabdq_s16
- arm_neon/vrhadd_u16
- arm_neon/vqshlq_n_u32
- arm_neon/vst4q_lane_u32
- arm_neon/vrsraq_n_u64
- arm_neon/vmlsq_n_s32
- arm_neon/vld4_u8
- arm_neon/vld2_f16
- arm_neon/vqshlq_u8
- arm_neon/vorrq_u64
- arm_neon/vmin_u16
- arm_neon/vext_u8
- arm_neon/vpaddl_s32
- arm_neon/vshlq_u64
- arm_neon/vst2q_lane_f16
- armintr/_arm_sbfx
- arm_neon/vld3_dup_f16
- armintr/_arm_uhasx
- arm_neon/vst2_lane_u8
- armintr/_arm_smultb
- arm_neon/vdup_n_p16
- arm_neon/vtrnq_u32
- arm_neon/vrshlq_u8
- arm_neon/vld4_lane_p16
- arm_neon/vsraq_n_s32
- arm_neon/vclt_s16
- arm_neon/vzip_u8
- arm_neon/vld3_lane_s16
- arm_neon/vceqq_s32
- arm_neon/vld3_dup_f32
- arm_neon/vld4q_lane_s32
- arm_neon/poly8x16x4_t
- arm_neon/uint64x1x2_t
- arm_neon/vqdmlal_n_s16
- arm_neon/vld2_dup_f16
- arm_neon/vshrq_n_s32
- arm_neon/vcleq_s8
- arm_neon/vld3_s32
- arm_neon/vqrshlq_s64
- arm_neon/vbsl_f32
- arm_neon/vext_s64
- arm_neon/vabaq_s32
- arm_neon/vmulq_s16
- arm_neon/vld3_lane_u16
- arm_neon/vld3q_lane_u16
- armintr/_arm_smlaltt
- arm_neon/poly8x8x2_t
- arm_neon/vst3q_u32
- armintr/_arm_smlsdx
- arm_neon/vqrshl_s64
- arm_neon/vextq_p8
- armintr/_arm_uhsub16
- arm_neon/vld3q_p8
- armintr/_arm_smlawt
- armintr/_arm_smlawb
- arm_neon/vdupq_lane_s8
- arm_neon/vaddl_s16
- arm_neon/vcombine_p16
- arm_neon/vzipq_u32
- arm_neon/poly16x8_t
- arm_neon/vshlq_n_s32
- arm_neon/vrshl_s8
- arm_neon/vst2_u64
- arm_neon/vrev64q_s8
- arm_neon/vst2q_lane_s32
- arm_neon/vld2_dup_s16
- arm_neon/vclt_u16
- arm_neon/vuzp_p8
- arm_neon/vshrq_n_s16
- arm_neon/vst3_u64
- arm_neon/vpmin_u16
- arm_neon/vld3q_lane_s32
- arm_neon/vmlal_s16
- arm_neon/poly16x4x4_t
- arm_neon/vorr_u16
- arm_neon/vsliq_n_s16
- arm_neon/vaddl_u8
- arm_neon/vld4_dup_s32
- arm_neon/vld2_f32
- arm_neon/vclt_u32
- arm_neon/vmull_lane_u16
- arm_neon/vsubw_u32
- arm_neon/vld2_dup_s32
- arm_neon/vuzp_s32
- arm_neon/vcge_s32
- arm_neon/vdup_lane_p16
- arm_neon/vpmin_s8
- arm_neon/vpaddlq_u32
- arm_neon/vmlaq_n_s32
- arm_neon/vshrn_n_u64
- arm_neon/vrshr_n_u16
- arm_neon/vld1_s64
- arm_neon/vbsl_u64
- armintr/_arm_smlad
- arm_neon/vqsub_s16
- arm_neon/vld4_p8
- arm_neon/vqdmulh_lane_s32
- arm_neon/vld3_dup_s64
- arm_neon/vornq_s32
- arm_neon/vpadd_u8
- arm_neon/vld3_lane_p16
- arm_neon/uint64x1x4_t
- arm_neon/vld3_u16
- armintr/_arm_shsax
- arm_neon/vabdq_u16
- arm_neon/vcgtq_f32
- arm_neon/vsubq_s8
- arm_neon/vget_low_f16
- arm_neon/vld4_dup_u64
- arm_neon/vst3_lane_s8
- armintr/_arm_ssat16
- arm_neon/vmlaq_f32
- arm_neon/vsri_n_s32
- arm_neon/vmax_u8
- arm_neon/vqadd_u8
- armintr/_arm_uqsub8
- armintr/_arm_clz
- arm_neon/vcgtq_s32
- arm_neon/vraddhn_s32
- arm_neon/vzip_s8
- arm_neon/veorq_s16
- arm_neon/vsetq_lane_s32
- arm_neon/vmul_n_u16
- armintr/_ReadBankedReg
- arm_neon/vld1q_u8
- arm_neon/vld4_p16
- arm_neon/int64x2x2_t
- arm_neon/vmaxq_s8
- arm_neon/vpmax_s16
- arm_neon/vshlq_u16
- arm_neon/vtrnq_p16
- arm_neon/vabal_u16
- arm_neon/vld2_lane_u16
- arm_neon/vrev32_u8
- arm_neon/vrshl_s32
- arm_neon/vget_low_f32
- arm_neon/vld2_s8
- arm_neon/vclzq_s16
- arm_neon/vqdmulhq_n_s16
- arm_neon/vset_lane_u64
- arm_neon/vld2_dup_p16
- arm_neon/vpaddlq_s32
- arm_neon/vld2q_p8
- arm_neon/vst3_lane_u8
- arm_neon/vld4_dup_f32
- arm_neon/vld2_s64
- arm_neon/vmls_u8
- arm_neon/vtbx4_u8
- arm_neon/vsetq_lane_f32
- arm_neon/vcvt_s32_f32
- arm_neon/vst3q_s32
- arm_neon/vmlsq_s8
- arm_neon/vmlaq_n_u16
- armintr/__iso_volatile_load64
- arm_neon/vcgt_u8
- arm_neon/vld2_dup_p8
- arm_neon/vmov_n_u8
- armintr/_arm_sasx
- arm_neon/vmovq_n_p16
- arm_neon/vmlaq_u32
- arm_neon/vst3_f32
- arm_neon/int32x2x4_t
- arm_neon/vld1q_lane_u64
- arm_neon/vclz_u16
- arm_neon/uint8x8_t
- arm_neon/vsub_u32
- arm_neon/vorn_u8
- armintr/__wfe
- arm_neon/vget_high_s16
- arm_neon/vzip_p8
- arm_neon/vmlal_lane_s16
- arm_neon/vmulq_u8
- armintr/_isunordered
- arm_neon/vld1_dup_f32
- arm_neon/vld4_lane_s16
- arm_neon/vdupq_n_s16
- arm_neon/vst3q_p16
- arm_neon/vst1_lane_f32
- arm_neon/float32x4x3_t
- arm_neon/vand_s8
- arm_neon/float32x2x4_t
- arm_neon/vld3_p8
- arm_neon/vmlaq_lane_u16
- armintr/_arm_uqsub16
- arm_neon/vget_high_s32
- arm_neon/vshl_n_s32
- arm_neon/vornq_s8
- arm_neon/vmlsl_n_u32
- arm_neon/vqshlq_n_s8
- arm_neon/int32x2x2_t
- arm_neon/int16x4x2_t
- arm_neon/vceqq_u8
- arm_neon/vcreate_f16
- arm_neon/vorn_s16
- arm_neon/vqmovn_s32
- arm_neon/vextq_u8
- arm_neon/vld4_s32
- armintr/_WriteStatusReg
- arm_neon/uint8x16_t
- arm_neon/vshrn_n_s64
- arm_neon/vmul_n_u32
- arm_neon/vabdl_u8
- arm_neon/vtbx3_s8
- arm_neon/vaddhn_s16
- arm_neon/vld3q_s8
- arm_neon/vmlsl_n_u16
- arm_neon/vrev64q_s32
- arm_neon/int16x8_t
- arm_neon/vext_s32
- arm_neon/vdupq_n_f32
- arm_neon/vld1q_lane_s32
- arm_neon/vqrshlq_u32
- arm_neon/vtbl2_u8
- arm_neon/vgetq_lane_u8
- arm_neon/veorq_u64
- arm_neon/vcntq_s8
- arm_neon/vbslq_p16
- arm_neon/vqnegq_s32
- arm_neon/vaddw_s32
- arm_neon/vmov_n_p8
- arm_neon/vmull_p8
- arm_neon/vld1_lane_u32
- arm_neon/vcombine_s16
- arm_neon/vqshrn_n_s64
- arm_neon/vceqq_s16
- arm_neon/vld4q_p16
- armintr/_ReadStatusReg
- armintr/_arm_qdadd
- arm_neon/uint32x4x2_t
- arm_neon/vcleq_u8
- armintr/_arm_sxtah
- arm_neon/vrhaddq_s32
- arm_neon/vset_lane_s64
- arm_neon/vld4_s64
- armintr/_DAddSatInt
- arm_neon/vorr_s8
- arm_neon/vst2_u32
- arm_neon/vshll_n_u16
- arm_neon/vld2_dup_u32
- arm_neon/vst3q_lane_s32
- arm_neon/vst3q_p8
- armintr/_MoveFromCoprocessor
- arm_neon/uint32x4_t
- arm_neon/vuzpq_s8
- arm_neon/vrecps_f32
- arm_neon/vst1_lane_s8
- arm_neon/vtbx1_s8
- arm_neon/uint16x8x3_t
- arm_neon/vpaddl_s16
- arm_neon/vsubq_s64
- arm_neon/vrsraq_n_u8
- arm_neon/vqadd_s64
- arm_neon/vst4_lane_s16
- arm_neon/vqadd_u16
- arm_neon/vset_lane_u32
- arm_neon/vand_u32
- arm_neon/vrsqrtsq_f32
- arm_neon/vqaddq_u32
- arm_neon/vsra_n_s64
- armintr/_arm_umlal
- arm_neon/vcvt_f32_f16
- arm_neon/vget_lane_u32
- arm_neon/vbsl_s8
- arm_neon/vrshlq_u32
- arm_neon/vqdmull_lane_s16
- arm_neon/vabsq_s32
- arm_neon/vld3_s8
- arm_neon/vst3q_lane_s16
- arm_neon/vld2q_lane_s16
- arm_neon/vst1_lane_s64
- arm_neon/vmov_n_u16
- arm_neon/vst4_lane_u8
- arm_neon/vshll_n_u32
- arm_neon/vqabs_s8
- arm_neon/vmvnq_u8
- arm_neon/vpadalq_u16
- arm_neon/vbsl_p16
- arm_neon/vqrshrn_n_u16
- arm_neon/vld3q_u32
- arm_neon/vcgeq_f32
- armintr/__iso_volatile_load32
- arm_neon/vrecpe_u32
- arm_neon/vld2_dup_u64
- arm_neon/vld3q_f32
- armintr/_arm_shsub8
- arm_neon/vdup_lane_s64
- arm_neon/vqrshl_s8
- arm_neon/vsliq_n_u16
- arm_neon/vld1q_u16
- arm_neon/vorr_u32
- arm_neon/vqrshl_s32
- armintr/__dmb
- arm_neon/veorq_s8
- arm_neon/vld1_u16
- arm_neon/vmov_n_u32
- arm_neon/vhsub_s16
- arm_neon/vst4q_lane_u16
- arm_neon/vbsl_u8
- armintr/_arm_uxtab
- arm_neon/vld2q_lane_f32
- arm_neon/vst2_p8
- armintr/_arm_smmla
- arm_neon/vaddw_u16
- arm_neon/vmlal_s8
- arm_neon/vtst_u32
- arm_neon/vtbl4_u8
- arm_neon/vcvt_n_f32_s32
- arm_neon/vcageq_f32
- arm_neon/vget_low_s16
- arm_neon/vdupq_n_u8
- arm_neon/vorn_s8
- arm_neon/uint8x16x3_t
- arm_neon/vabdq_u32
- arm_neon/vrev64_p8
- arm_neon/vqsubq_s8
- armintr/_arm_smlabb
- arm_neon/vbicq_s64
- arm_neon/vmaxq_u16
- arm_neon/vdup_n_u8
- arm_neon/veor_s8
- arm_neon/int16x8x2_t
- arm_neon/vcvtq_s32_f32
- arm_neon/vtrn_u16
- arm_neon/vbslq_s32
- arm_neon/vld1q_dup_u32
- arm_neon/vmul_n_f32
- arm_neon/vqrshl_u32
- arm_neon/vqsubq_s16
- arm_neon/vst2_lane_f16
- armintr/_arm_smulwt
- arm_neon/vrshrn_n_u32
- arm_neon/vget_high_p16
- arm_neon/vqadd_u64
- arm_neon/vsli_n_s32
- arm_neon/vhadd_u32
- arm_neon/vmlsl_lane_u16
- arm_neon/vclzq_u32
- arm_neon/vqshrun_n_s64
- arm_neon/vrev64q_u32
- arm_neon/vqshrun_n_s16
- arm_neon/vrev32q_s8
- armintr/_arm_shasx
- arm_neon/vaddl_s8
- armintr/_arm_smull
- arm_neon/vabaq_u8
- armintr/_arm_revsh
- arm_neon/vsubq_f32
- arm_neon/poly16x4x2_t
- arm_neon/poly8x8x3_t
- arm_neon/vsubhn_s64
- arm_neon/vcle_u16
- arm_neon/poly8x16x3_t
- arm_neon/vqdmlsl_n_s16
- arm_neon/vqshl_u64
- arm_neon/vcge_u16
- armintr/_arm_uasx
- arm_neon/vmovl_s32
- arm_neon/vst1q_lane_u16
- arm_neon/vbic_u32
- arm_neon/vld2_s16
- armintr/_arm_qasx
- arm_neon/vorrq_u8
- arm_neon/vst2_s32
- armintr/_WriteBankedReg
- arm_neon/veorq_s64
- arm_neon/vld4_lane_f32
- arm_neon/vcreate_u8
- arm_neon/vset_lane_u8
- arm_neon/vandq_u16
- arm_neon/vrsubhn_s64
- arm_neon/vst1q_lane_p16
- arm_neon/uint8x8x2_t
- arm_neon/vmlsl_s8
- arm_neon/vmax_s32
- arm_neon/uint32x4x3_t
- arm_neon/vld4_dup_u16
- arm_neon/vabs_s32
- arm_neon/vld3_dup_u32
- arm_neon/vrshl_u16
- arm_neon/vcle_u8
- arm_neon/vqshl_n_u16
- arm_neon/vbic_s8
- arm_neon/float32x4x2_t
- arm_neon/vmls_f32
- arm_neon/vshll_n_u8
- arm_neon/vminq_s8
- arm_neon/vmlsq_lane_f32
- arm_neon/vst1q_f16
- arm_neon/vst1_lane_u64
- arm_neon/vrhadd_u8
- arm_neon/vclt_s32
- arm_neon/vst2_p16
- arm_neon/vrshrq_n_u16
- arm_neon/vneg_s32
- arm_neon/vmovl_s16
- arm_neon/vqshlq_s8
- arm_neon/vld1_s8
- arm_neon/vqdmulh_s32
- arm_neon/vcls_s8
- armintr/__trap
- arm_neon/vuzp_u32
- armintr/_CopyInt64FromDouble
- arm_neon/int8x16x2_t
- arm_neon/vmovn_s32
- arm_neon/vget_high_s8
- arm_neon/veor_s64
- armintr/_arm_uadd8
- arm_neon/vrev16_u8
- arm_neon/vbicq_u64
- arm_neon/vst4_lane_f16
- arm_neon/vst3_s32
- arm_neon/poly8x8_t
- arm_neon/vtstq_u16
- arm_neon/vld1_lane_s8
- arm_neon/float32x4x4_t
- arm_neon/vst2_s16
- arm_neon/vqrdmulhq_s32
- arm_neon/vqdmulhq_s16
- arm_neon/vrshrq_n_s8
- arm_neon/vcle_s32
- arm_neon/vtbl3_p8
- arm_neon/vbslq_u8
- arm_neon/vst4_u64
- armintr/_arm_umaal
- arm_neon/vshll_n_s8
- arm_neon/vcvt_u32_f32
- arm_neon/vld4q_p8
- arm_neon/vsetq_lane_u16
- arm_neon/vabd_u8
- arm_neon/vclz_u8
- arm_neon/vsubq_u32
- arm_neon/vld1q_lane_p16
- arm_neon/vcgtq_s16
- arm_neon/vmla_lane_s32
- arm_neon/vshlq_n_s64
- arm_neon/vbsl_u32
- arm_neon/vqshlq_s16
- armintr/_arm_qadd8
- arm_neon/vrshr_n_s32
- armintr/_CountOneBits64
- arm_neon/vceq_u32
- arm_neon/vbsl_p8
- arm_neon/uint16x8x2_t
- arm_neon/vsli_n_s16
- arm_neon/vmla_n_s32
- arm_neon/vld4_dup_u32
- arm_neon/vshrq_n_s8
- arm_neon/vqaddq_s8
- arm_neon/vshl_n_u64
- arm_neon/vtbl2_p8
- arm_neon/vcleq_u32
- arm_neon/vqsub_u32
- arm_neon/vmovl_u8
- arm_neon/vmlal_u8
- arm_neon/vmul_s8
- armintr/_MoveFromCoprocessor64
- arm_neon/vrsraq_n_s16
- arm_neon/vdupq_n_u32
- arm_neon/vmov_n_s16
- arm_neon/vst4_lane_p8
- arm_neon/vld1_s32
- arm_neon/vst4_p8
- arm_neon/vsriq_n_u32
- arm_neon/vqdmull_n_s16
- arm_neon/vshlq_u32
- arm_neon/vld3_u8
- armintr/_arm_usub16
- arm_neon/vmlsq_lane_s16
- arm_neon/vmovq_n_s8
- arm_neon/int32x4x2_t
- arm_neon/vld4q_u8
- arm_neon/poly16x8x2_t
- arm_neon/vld1q_u64
- arm_neon/vld3q_lane_s16
- arm_neon/int64x1x2_t
- arm_neon/vshlq_n_s8
- arm_neon/vrshl_s64
- arm_neon/vqshl_n_u8
- armintr/_arm_qadd
- armintr/_DSubSatInt
- armintr/_arm_usat16
- arm_neon/vmull_s8
- arm_neon/vsub_s8
- arm_neon/vmovq_n_u16
- arm_neon/vst4_u16
- arm_neon/vmlsl_lane_u32
- arm_neon/vsliq_n_p16
- arm_neon/vmovn_u32
- arm_neon/vbic_u16
- arm_neon/vtbx2_p8
- arm_neon/vrsubhn_s32
- armintr/_SubSatInt
- arm_neon/vst3_u8
- arm_neon/vdupq_n_s32
- arm_neon/vcntq_p8
- arm_neon/vst4_f32
- arm_neon/vbic_s64
- arm_neon/vld3_s64
- arm_neon/vrsra_n_s64
- arm_neon/vqabsq_s16
- arm_neon/vsriq_n_p8
- arm_neon/vst2_lane_p16
- arm_neon/vabsq_s16
- arm_neon/vcombine_u8
- arm_neon/vld2q_p16
- armintr/_CountOneBits
- armintr/__prefetch
- arm_neon/vld3_dup_u64
- arm_neon/vld2q_s16
- arm_neon/vget_low_p16
- arm_neon/vuzpq_u8
- arm_neon/vrev32q_s16
- armintr/_AddSatInt
- arm_neon/uint16x4x2_t
- arm_neon/vmov_n_s32
- arm_neon/vaddl_u16
- arm_neon/vqaddq_s64
- arm_neon/vmlaq_u16
- arm_neon/vsli_n_s8
- armintr/_arm_sxth
- arm_neon/vorr_s32
- arm_neon/vsra_n_u64
- arm_neon/vst2_f16
- arm_neon/vcombine_u16
- arm_neon/vabs_s16
- arm_neon/vsubhn_s32
- arm_neon/vst1q_lane_u32
- arm_neon/vst3_p8
- arm_neon/vqshrun_n_s32
- arm_neon/vcreate_s64
- arm_neon/vld4q_lane_s16
- arm_neon/vzipq_u16
- arm_neon/vmin_s32
- armintr/_CopyInt32FromFloat
- arm_neon/vcgtq_u32
- arm_neon/vabdl_s32
- arm_neon/vqshlq_n_u16
- arm_neon/int8x16x4_t
- arm_neon/vqrdmulh_n_s32
- arm_neon/vqaddq_u64
- arm_neon/vhaddq_s8
- arm_neon/vshll_n_s16
- arm_neon/vuzp_u8
- arm_neon/vaddl_u32
- arm_neon/vld4q_s16
- arm_neon/vqmovun_s16
- arm_neon/vld1q_lane_s8
- arm_neon/vld2_lane_u32
- arm_neon/vrshr_n_s8
- arm_neon/vmlaq_s16
- armintr/_CopyFloatFromInt32
- arm_neon/vmul_f32
- arm_neon/vmlaq_n_f32
- arm_neon/vst4_s16
- arm_neon/vld1_dup_s32
- arm_neon/vmul_u16
- arm_neon/vhaddq_s16
- arm_neon/vst1q_lane_f32
- arm_neon/vrhaddq_u16
- arm_neon/vbicq_u32
- arm_neon/vrev32_s8
- arm_neon/vmlaq_s8
- arm_neon/vmin_s16
- arm_neon/vst3_lane_p16
- arm_neon/vst2q_lane_f32
- arm_neon/vld4q_lane_f32
- arm_neon/vget_low_u16
- arm_neon/vqsub_s32
- arm_neon/vtbl1_s8
- arm_neon/vmovn_s64
- arm_neon/vpmax_s8
- arm_neon/int8x16_t
- arm_neon/vpmin_u8
- arm_neon/vdup_lane_p8
- arm_neon/vsetq_lane_u64
- arm_neon/vuzpq_u16
- arm_neon/vcgeq_u16
- arm_neon/uint8x16x2_t
- armintr/_arm_rev16
- armintr/_arm_sxtb
- arm_neon/vsliq_n_u64
- arm_neon/vmovq_n_u8
- arm_neon/vshlq_n_u32
- arm_neon/vcombine_s64
- armintr/_arm_qsax
- arm_neon/vmin_f32
- armintr/_arm_sadd16
- arm_neon/vmlsq_n_s16
- arm_neon/vorr_u64
- arm_neon/vqrshrun_n_s64
- arm_neon/vld2q_lane_s32
- arm_neon/vgetq_lane_p16
- arm_neon/vrev32_s16
- arm_neon/vqshl_u16
- arm_neon/vtrn_s8
- arm_neon/vst1q_lane_s64
- arm_neon/vtbl4_p8
- arm_neon/vst1_p16
- arm_neon/vmvn_u8
- arm_neon/vld2_lane_u8
- arm_neon/vld2q_u16
- arm_neon/vmovl_s8
- arm_neon/vbslq_u64
- arm_neon/vmls_s8
- arm_neon/vld3q_p16
- arm_neon/vtbl3_u8
- arm_neon/vabs_f32
- arm_neon/vsraq_n_s8
- arm_neon/vqadd_s32
- arm_neon/vmulq_n_s16
- arm_neon/vst3q_s8
- arm_neon/vaddhn_s64
- arm_neon/vmul_n_s16
- arm_neon/vtbl1_p8
- arm_neon/uint64x2x3_t
- arm_neon/vmlsq_s32
- arm_neon/vld2q_lane_u32
- arm_neon/vaddq_u8
- arm_neon/vcombine_f16
- arm_neon/vandq_s16
- arm_neon/vst4q_lane_p16
- arm_neon/vsri_n_u8
- arm_neon/vst3_lane_p8
- arm_neon/vst3_lane_s16
- arm_neon/vdup_n_s16
- arm_neon/vbicq_s8
- arm_neon/vdup_lane_u8
- arm_neon/vst4q_lane_s32
- arm_neon/vqrshl_u16
- arm_neon/vrsra_n_u32
- arm_neon/vdupq_lane_p8
- arm_neon/vld3_lane_u8
- arm_neon/vqrdmulh_n_s16
- arm_neon/vpmin_s32
- armintr/__cps
- arm_neon/vshl_u32
- armintr/_arm_uadd16
- arm_neon/vld3_s16
- arm_neon/vcvt_f32_s32
- arm_neon/vshlq_n_u64
- arm_neon/vrev64q_u8
- arm_neon/vextq_u16
- arm_neon/vsubl_s16
- arm_neon/vget_lane_p8
- arm_neon/vabal_s16
- arm_neon/vrecpeq_u32
- arm_neon/vminq_u8
- arm_neon/veor_s16
- arm_neon/vmull_n_u16
- arm_neon/vshl_n_u8
- arm_neon/vrev32q_u8
- arm_neon/vandq_s8
- arm_neon/vrshlq_s16
- arm_neon/vst4q_p16
- arm_neon/vandq_s32
- armintr/_MoveToCoprocessor2
- arm_neon/vqdmlsl_lane_s32
- arm_neon/vld1q_s64
- arm_neon/vmull_n_s16
- arm_neon/vneg_s16
- arm_neon/vqshluq_n_s64
- arm_neon/vst2_lane_s32
- arm_neon/vmvnq_u16
- arm_neon/vshll_n_s32
- arm_neon/vld3_dup_s8
- arm_neon/vtstq_s32
- arm_neon/vmlsl_u32
- arm_neon/vqdmulhq_lane_s16
- arm_neon/vaddl_s32
- armintr/_CountLeadingZeros
- arm_neon/vqrshrn_n_s16
- arm_neon/vmla_lane_u32
- arm_neon/vst1_u8
- arm_neon/vshl_u64
- arm_neon/vshr_n_u8
- arm_neon/vmull_lane_s32
- arm_neon/vmlal_lane_u32
- arm_neon/vsubl_s8
- arm_neon/float32x2x2_t
- armintr/_arm_bfc
- arm_neon/vaddq_s16
- arm_neon/vmlal_lane_s32
- arm_neon/vpadd_u16
- arm_neon/vst2q_lane_u16
- arm_neon/vld4_s8
- arm_neon/vst1q_s8
- arm_neon/vshrq_n_u64
- arm_neon/vsli_n_u16
- arm_neon/vqrdmulh_lane_s32
- arm_neon/vst4_lane_u16
- arm_neon/vabdq_f32
- arm_neon/vld2_lane_f16
- arm_neon/vqsub_u64
- arm_neon/vsub_f32
- arm_neon/vld1q_s16
- arm_neon/vmaxq_s16
- arm_neon/vcombine_u32
- arm_neon/vrsraq_n_u32
- armintr/_arm_smusdx
- arm_neon/vrev16_s8
- arm_neon/vqdmulh_n_s32
- arm_neon/vmul_s32
- arm_neon/vabdq_s32
- arm_neon/veor_u64
- arm_neon/vmlsl_n_s32
- arm_neon/vsub_s16
- arm_neon/vadd_u16
- arm_neon/vsriq_n_u16
- arm_neon/vmla_u32
- arm_neon/vuzpq_s32
- arm_neon/vst4q_s8
- arm_neon/vaddhn_u32
- arm_neon/vmlaq_lane_f32
- arm_neon/vld3_lane_s8
- arm_neon/vsliq_n_u32
- arm_neon/vqrshlq_s8
- arm_neon/vqdmlal_n_s32
- arm_neon/uint8x16x4_t
- arm_neon/vcgtq_u16
- arm_neon/vandq_u32
- arm_neon/vld4q_lane_u32
- arm_neon/vzip_p16
- arm_neon/vget_low_p8
- armintr/_arm_shadd8
- arm_neon/vmovn_s16
- arm_neon/vcge_u8
- arm_neon/vld2q_f32
- arm_neon/vaba_u32
- armintr/__iso_volatile_store8
- arm_neon/vst2q_p16
- arm_neon/vmul_s16
- arm_neon/vand_s16
- arm_neon/vtbx4_p8
- arm_neon/vceq_u8
- arm_neon/vrhaddq_s16
- arm_neon/vgetq_lane_f32
- arm_neon/vqshl_s8
- arm_neon/vbslq_f32
- arm_neon/vrsqrts_f32
- arm_neon/vld2q_s8
- arm_neon/vtbl1_u8
- arm_neon/vtst_u8
- arm_neon/vrev64q_f32
- arm_neon/vcle_s8
- arm_neon/vsetq_lane_p16
- arm_neon/vcreate_p16
- arm_neon/vabal_s32
- armintr/_arm_smlald
- arm_neon/vmla_f32
- arm_neon/vtbx2_s8
- arm_neon/int64x1x3_t
- arm_neon/vclz_s8
- arm_neon/vorr_s16
- arm_neon/vornq_s64
- arm_neon/vst1q_u64
- arm_neon/vdupq_n_s8
- armintr/_arm_sadd8
- arm_neon/vextq_s32
- armintr/_arm_smuadx
- armintr/_arm_qsub
- arm_neon/vadd_f32
- arm_neon/vrshrq_n_s16
- arm_neon/vqsub_s8
- arm_neon/vld3_f32
- arm_neon/vhadd_s8
- arm_neon/vmull_n_u32
- arm_neon/vdup_n_u64
- arm_neon/vsubw_s32
- armintr/_arm_sxtab
- armintr/_arm_uxtb16
- arm_neon/vmvn_s16
- arm_neon/vst1_lane_s16
- arm_neon/vqrdmulhq_n_s32
- arm_neon/vsriq_n_s32
- arm_neon/poly8x16x2_t
- arm_neon/vadd_u8
- arm_neon/vuzpq_p8
- arm_neon/vst2q_p8
- armintr/__wfi
- arm_neon/vget_high_u16
- arm_neon/vqrshl_u64
- arm_neon/vld1_dup_s64
- arm_neon/vqrshrn_n_s32
- arm_neon/vrshr_n_s64
- arm_neon/vst3_s8
- arm_neon/poly16x4x3_t
- arm_neon/vqrdmulh_lane_s16
- arm_neon/vmvnq_u32
- arm_neon/vqsubq_u32
- arm_neon/vmovq_n_p8
- arm_neon/vtrn_s16
- arm_neon/vld2q_u32
- arm_neon/vqsubq_u16
- arm_neon/vrsqrteq_u32
- arm_neon/vadd_u64
- armintr/_arm_usat
- arm_neon/vcvtq_n_u32_f32
- arm_neon/vaddq_s8
- arm_neon/vrsraq_n_u16
- arm_neon/vqabs_s16
- arm_neon/vsra_n_s8
- arm_neon/vsra_n_s16
- arm_neon/vqshlq_n_u8
- arm_neon/vpadal_s8
- arm_neon/vmlal_n_u16
- armintr/_CopyDoubleFromInt64
- arm_neon/vaddw_u8
- arm_neon/vmulq_n_s32
- arm_neon/vqaddq_s32
- arm_neon/vmla_lane_f32
- arm_neon/vmlaq_lane_s32
- arm_neon/vld1q_dup_u64
- arm_neon/uint16x8_t
- arm_neon/vld2_s32
- arm_neon/vcltq_f32
- arm_neon/vst4q_f32
- arm_neon/vsri_n_u16
- arm_neon/vshlq_s32
- arm_neon/vgetq_lane_u32
- arm_neon/vld1q_dup_f16
- arm_neon/vrev64q_s16
- arm_neon/vrshrq_n_u32
- arm_neon/vld2q_s32
- arm_neon/vcgtq_s8
- arm_neon/vsubhn_u64
- arm_neon/vmls_n_s32
- armintr/_arm_smmlar
- arm_neon/vld3_dup_u8
- arm_neon/vld3q_lane_p16
- arm_neon/vld2_dup_s64
- arm_neon/vqabs_s32
- arm_neon/vqaddq_u8
- arm_neon/vminq_u32
- arm_neon/vpaddl_u16
- arm_neon/vaba_s16
- arm_neon/vmul_u32
- arm_neon/vst1_lane_u16
- arm_neon/vcreate_f32
- arm_neon/vcvt_f16_f32
- arm_neon/vset_lane_s32
- arm_neon/vshl_s8
- arm_neon/vcgt_s16
- arm_neon/vtrn_f32
- arm_neon/vget_high_s64
- arm_neon/vld3_dup_p8
- arm_neon/vcreate_u64
- arm_neon/vext_u64
- arm_neon/vld1q_dup_s16
- arm_neon/vget_lane_s16
- arm_neon/vqdmlal_s16
- arm_neon/vld2_p16
- arm_neon/vld4_u16
- armintr/_arm_smlalbb
- arm_neon/vrev64_u8
- arm_neon/vbslq_s64
- arm_neon/vsubw_u16
- arm_neon/vrsubhn_u32
- arm_neon/vabdq_u8
- arm_neon/vmls_n_u32
- arm_neon/vshr_n_s32
- arm_neon/vmulq_n_u32
- arm_neon/vst3_p16
- arm_neon/vrev32_u16
- arm_neon/int8x8x3_t
- arm_neon/vst2q_lane_u32
- arm_neon/vextq_p16
- arm_neon/vtrnq_f32
- armintr/_arm_smultt
- arm_neon/vqneg_s8
- arm_neon/vmlsq_lane_s32
- arm_neon/vmov_n_p16
- arm_neon/vraddhn_u64
- arm_neon/vrhadd_u32
- arm_neon/vrev64_u32
- arm_neon/vrshrn_n_s32
- arm_neon/vld4q_f32
- arm_neon/vst2_s8
- arm_neon/vrsqrteq_f32
- arm_neon/uint16x4_t
- arm_neon/vget_low_s8
- arm_neon/vst2_lane_u32
- arm_neon/vhsub_s32
- arm_neon/vqdmull_lane_s32
- armintr/_arm_smulwb
- arm_neon/vmlsl_u8
- arm_neon/vdup_lane_s16
- arm_neon/vtbx4_s8
- arm_neon/vld4q_lane_u16
- arm_neon/vget_high_u8
- arm_neon/vclzq_s32
- arm_neon/vld1q_dup_f32
- arm_neon/vtrn_u8
- arm_neon/vqabsq_s8
- arm_neon/vdup_lane_f32
- arm_neon/vqrdmulh_s16
- arm_neon/vst4_u32
- arm_neon/vdup_lane_u32
- arm_neon/vst4_u8
- arm_neon/vmovq_n_s32
- arm_neon/vld2_lane_s8
- arm_neon/vld3_u32
- arm_neon/vsubl_u16
- arm_neon/vqshlu_n_s8
- arm_neon/float32x4_t
- arm_neon/vqshl_n_s32
- arm_neon/float32x2x3_t
- armintr/__hvc
- arm_neon/vst1q_lane_f16
- arm_neon/vmvnq_s16
- arm_neon/vst3q_lane_f32
- arm_neon/vld1q_dup_u8
- arm_neon/vmlsq_s16
- arm_neon/vget_lane_u8
- arm_neon/vld1_lane_s32
- arm_neon/vst4q_s16
- armintr/_arm_qsub8
- arm_neon/vorrq_s32
- arm_neon/vsriq_n_s8
- arm_neon/vqshrn_n_u64
- arm_neon/vdup_n_s32
- armintr/_arm_uhsub8
- arm_neon/vld3_lane_s32
- arm_neon/vbsl_s64
- arm_neon/vld1_dup_f16
- arm_neon/vsli_n_u64
- arm_neon/vraddhn_u32
- arm_neon/vsub_u16
- arm_neon/vcltq_u32
- arm_neon/vminq_f32
- arm_neon/vshl_n_s64
- arm_neon/vld4_u32
- arm_neon/vld1_u32
- arm_neon/vaddhn_u16
- arm_neon/vcvtq_n_f32_s32
- arm_neon/vorn_u64
- arm_neon/vsubhn_u16
- arm_neon/int64x1_t
- arm_neon/vst1q_lane_s8
- arm_neon/vld1q_dup_s32
- arm_neon/vrev32_p8
- arm_neon/vst3q_lane_p16
- arm_neon/vrecpeq_f32
- arm_neon/int8x8x4_t
- arm_neon/vshr_n_u32
- arm_neon/vdupq_lane_s64
- arm_neon/vpaddlq_s8
- arm_neon/vqshl_n_u32
- arm_neon/vmul_u8
- arm_neon/vtbx2_u8
- arm_neon/vshr_n_u64
- arm_neon/vqrshlq_s16
- arm_neon/vst3_lane_u16
- arm_neon/vqsub_u8
- arm_neon/vrsra_n_s16
- arm_neon/vaba_s32
- arm_neon/vsri_n_u64
- arm_neon/vst3q_lane_u32
- arm_neon/vmlsq_n_u32
- arm_neon/poly8x16_t
- arm_neon/vld2_u8
- armintr/_arm_smmulr
- arm_neon/vtst_s16
- armintr/_arm_smmls
- arm_neon/vqdmulh_s16
- arm_neon/vtrnq_u8
- arm_neon/vset_lane_p8
- arm_neon/vmlsl_u16
- arm_neon/vshrn_n_u16
- arm_neon/vld1_dup_p8
- arm_neon/vrev16q_s8
- arm_neon/vmov_n_s8
- arm_neon/vld1_u64
- arm_neon/vpmin_f32
- arm_neon/vmla_n_u16
- arm_neon/vst1_f16
- arm_neon/vqdmlsl_s16
- arm_neon/vmin_u32
- armintr/_arm_qsub16
- arm_neon/vcage_f32
- arm_neon/vornq_u32
- arm_neon/vpadd_s16
- arm_neon/vld1_u8
- arm_neon/vhsubq_s16
- arm_neon/vld1_dup_u32
- arm_neon/vld4_u64
- armintr/_MulHigh
- arm_neon/vmaxq_u8
- arm_neon/vget_lane_u16
- arm_neon/vld2q_u8
- arm_neon/vld1q_dup_p16
- arm_neon/vsraq_n_u8
- arm_neon/vqdmlsl_n_s32
- arm_neon/vst1_s16
- arm_neon/vst1q_s32
- arm_neon/vmaxq_f32
- arm_neon/vqdmulh_lane_s16
- armintr/__isb
- arm_neon/vuzpq_p16
- arm_neon/vmls_lane_s16
- arm_neon/vtbl4_s8
- arm_neon/vst1_lane_p8
- arm_neon/vsubw_s8
- arm_neon/vmin_u8
- arm_neon/vzip_u16
- arm_neon/vld4q_u16
- arm_neon/vshrn_n_s32
- arm_neon/vpadal_u16
- arm_neon/vorrq_s8
- arm_neon/vrshlq_u64
- arm_neon/vst3_lane_s32
- arm_neon/vqshluq_n_s32
- armintr/_arm_shsub16
- arm_neon/vst1_u32
- arm_neon/vrhadd_s16
- arm_neon/vzipq_s32
- arm_neon/vshrq_n_u16
- arm_neon/vcls_s32
- arm_neon/vceq_s8
- arm_neon/vld2q_lane_f16
- arm_neon/vst4q_u8
- arm_neon/vraddhn_u16
- arm_neon/vget_lane_u64
- armintr/_arm_smlsld
- arm_neon/vld3_u64
- arm_neon/vld1_lane_s16
- arm_neon/vabd_f32
- arm_neon/vdupq_n_u16
- armintr/__iso_volatile_store64
- arm_neon/vqsubq_u8
- arm_neon/poly16x8x3_t
- arm_neon/vcltq_s32
- arm_neon/vqnegq_s16
- arm_neon/vqsub_u16
- arm_neon/vaddq_s32
- arm_neon/vqshl_n_s64
- arm_neon/vabdl_s8
- arm_neon/vclsq_s16
- arm_neon/vpaddl_u8
- arm_neon/vmlsq_n_u16
- armintr/_arm_uqadd8
- arm_neon/vhsub_u32
- arm_neon/vset_lane_s16
- arm_neon/vsubl_u32
- arm_neon/vld3_lane_f32
- arm_neon/vcle_s16
- arm_neon/vmovl_u32
- arm_neon/vst3_lane_f16
- arm_neon/vcaltq_f32
- arm_neon/vsubq_s32
- arm_neon/vand_s64
- arm_neon/vst2_u8
- arm_neon/vcombine_p8
- arm_neon/vqdmlal_s32
- arm_neon/vsub_s32
- armintr/_arm_uxtab16
- arm_neon/vmlsq_n_f32
- armintr/_arm_qdsub
- arm_neon/vhaddq_u32
- arm_neon/vhsubq_u16
- arm_neon/vmlsq_lane_u16
- arm_neon/vst4_s64
- armintr/_CountLeadingOnes
- armintr/_arm_smlabt
- arm_neon/vcombine_s32
- arm_neon/vld4_lane_f16
- arm_neon/vadd_s64
- arm_neon/vorrq_u32
- armintr/__sev
- arm_neon/vdupq_lane_s32
- arm_neon/vrecpsq_f32
- arm_neon/vbicq_u16
- arm_neon/vld1_lane_p16
- arm_neon/vrshr_n_u32
- arm_neon/vcgeq_s32
- arm_neon/vld4_dup_s16
- arm_neon/vld1q_p8
- arm_neon/vrshlq_u16
- arm_neon/vmlaq_lane_u32
- arm_neon/vsub_s64
- arm_neon/vcreate_u16
- arm_neon/vget_lane_s32
- arm_neon/vuzp_f32
- arm_neon/vld2_lane_p8
- arm_neon/vuzp_u16
- arm_neon/vorrq_s16
- armintr/_arm_smlaltb
- arm_neon/vrshrn_n_s16
- arm_neon/vabd_s8
- arm_neon/vnegq_s8
- arm_neon/vst4q_u16
- arm_neon/vst1q_lane_s32
- arm_neon/vst1_lane_s32
- arm_neon/vmla_u16
- arm_neon/vmls_lane_s32
- arm_neon/vtst_s8
- arm_neon/vcgeq_s8
- arm_neon/poly8x8x4_t
- arm_neon/vqsub_s64
- armintr/_arm_uqasx
- arm_neon/vld1_lane_u64
- arm_neon/vminq_s16
- arm_neon/vmulq_u32
- arm_neon/vqrshlq_u8
- arm_neon/vdupq_n_p16
- arm_neon/vld4_dup_f16
- arm_neon/vcls_s16
- arm_neon/vmov_n_u64
- arm_neon/vmla_s32
- arm_neon/vrshl_s16
- arm_neon/vcalt_f32
- arm_neon/int64x2x3_t
- arm_neon/vsub_u8
- arm_neon/vzipq_u8
- arm_neon/vrshrn_n_u64
- arm_neon/vrshlq_s32
- arm_neon/vorr_s64
- arm_neon/vqrshl_s16
- arm_neon/vceqq_u16
- arm_neon/vmulq_n_u16
- arm_neon/vmlaq_u8
- arm_neon/vsri_n_s64
- arm_neon/vld3q_u8
- arm_neon/vld1_dup_s16
- arm_neon/vld1q_s32
- arm_neon/vsri_n_s16
- arm_neon/vshlq_u8
- arm_neon/vsli_n_s64
- arm_neon/vmull_lane_u32
- arm_neon/vshl_s64
- arm_neon/vcreate_s16
- arm_neon/uint8x8x4_t
- arm_neon/vqshrn_n_s32
- arm_neon/vqshlq_u32
- arm_neon/vmlal_n_u32
- arm_neon/vtrnq_s16
- arm_neon/vshr_n_s64
- arm_neon/vst2_u16
- arm_neon/vtrn_s32
- arm_neon/vsubhn_u32
- arm_neon/vbicq_s16
- arm_neon/vsetq_lane_s8
- arm_neon/vrsubhn_s16
- arm_neon/vhsub_u8
- arm_neon/vcleq_s32
- arm_neon/vld4_dup_s8
- arm_neon/vmull_u32
- arm_neon/vrshr_n_s16
- arm_neon/vst1q_lane_s16
- arm_neon/vmlsq_lane_u32
- arm_neon/vnegq_f32
- arm_neon/vmin_s8
- arm_neon/vrev16_p8
- arm_neon/vbic_u8
- arm_neon/vclzq_u16
- arm_neon/vcge_u32
- arm_neon/vget_high_u64
- arm_neon/vabsq_s8
- arm_neon/vhaddq_u16
- arm_neon/vsraq_n_s64
- arm_neon/vld2_u32
- arm_neon/vld2_lane_f32
- arm_neon/vqrshrn_n_u32
- arm_neon/vbslq_s8
- armintr/_CountLeadingZeros64
- arm_neon/vbicq_u8
- arm_neon/vdup_lane_s8
- arm_neon/vpadd_s32
- arm_neon/vld3q_lane_f16
- arm_neon/vaba_u8
- arm_neon/vqshlq_u16
- arm_neon/vst1q_u8
- arm_neon/vst4q_lane_f16
- arm_neon/vshl_n_u16
- armintr/_arm_smladx
- arm_neon/vmla_lane_s16
- arm_neon/vornq_u8
- arm_neon/vqneg_s32
- arm_neon/vadd_s8
- arm_neon/vcle_u32
- arm_neon/vclzq_u8
- arm_neon/vtbx1_u8
- armintr/_CountLeadingOnes64
- armintr/__dsb
- arm_neon/vaddq_u32
- arm_neon/vclsq_s8
- arm_neon/vdup_n_s64
- arm_neon/vmax_s16
- arm_neon/vst2q_u32
- arm_neon/vsetq_lane_s64
- arm_neon/vtst_p8
- arm_neon/vabs_s8
- arm_neon/vqshl_n_s16
- arm_neon/vqrshrn_n_u64
- arm_neon/vaddw_s8
- armintr/_arm_uhadd16
- arm_neon/vsriq_n_p16
- arm_neon/vld4_lane_u32
- arm_neon/vneg_f32
- armintr/_MoveToCoprocessor
- arm_neon/vmvnq_s8
- arm_neon/vld1q_lane_p8
- arm_neon/uint32x2x3_t
- arm_neon/vrshrn_n_u16
- arm_neon/vld3_f16
- arm_neon/vsriq_n_s16
- arm_neon/vshlq_n_s16
- arm_neon/vabal_u8
- arm_neon/vqshluq_n_s16
- arm_neon/vst2_lane_u16
- arm_neon/vbic_s16
- arm_neon/vqshl_n_u64
- arm_neon/vcagt_f32
- arm_neon/vpadalq_s8
- arm_neon/vclz_s32
- arm_neon/vld1_lane_s64
- arm_neon/vget_high_p8
- arm_neon/uint64x1_t
- arm_neon/vextq_s16
- arm_neon/vpadd_s8
- arm_neon/vrsubhn_u64
- arm_neon/vst3q_f16
- arm_neon/vdupq_lane_u16
- arm_neon/vrshrq_n_u64
- arm_neon/vmovq_n_f32
- arm_neon/vld1q_dup_u16
- arm_neon/vshr_n_u16
- arm_neon/uint32x2_t
- armintr/_arm_umull
- arm_neon/vtrnq_u16
- arm_neon/vsetq_lane_u32
- arm_neon/vneg_s8
- arm_neon/vsetq_lane_u8
- arm_neon/vst2q_lane_s16
- arm_neon/vqmovun_s32
- armintr/_arm_usad8
- armintr/_arm_pkhbt
- arm_neon/uint16x4x3_t
- arm_neon/vsra_n_s32
- arm_neon/vqmovun_s64
- arm_neon/vld1q_dup_s8
- arm_neon/vaddhn_s32
- arm_neon/vpmax_f32
- arm_neon/vpadd_u32
- arm_neon/vhsubq_u32
- arm_neon/vqrshrun_n_s32
- arm_neon/vadd_s32
- arm_neon/vclt_s8
- arm_neon/vorrq_s64
- arm_neon/vst4q_f16
- arm_neon/vst1_s32
- arm_neon/vceq_p8
- arm_neon/vsubw_s16
- arm_neon/vgetq_lane_u64
- arm_neon/vmla_n_u32
- arm_neon/vcvtq_f32_s32
- arm_neon/vld1q_u32
- arm_neon/vmax_f32
- armintr/_isunorderedf
- arm_neon/vrshl_u8
- arm_neon/vld4_dup_s64
- arm_neon/vqaddq_u16
- arm_neon/vld4q_lane_f16
- arm_neon/vceqq_p8
- arm_neon/vsubw_u8
- arm_neon/vqmovn_u16
- armintr/_arm_smlsldx
- arm_neon/vcreate_p8
- arm_neon/vqdmull_n_s32
- arm_neon/uint64x2_t
- arm_neon/vmls_s32
- arm_neon/vst3q_f32
- armintr/_arm_bfi
- armintr/_arm_qadd16
- arm_neon/vrshlq_s8
- arm_neon/vget_lane_p16
- arm_neon/vld2_p8
- arm_neon/vld3_lane_u32
- armintr/_MoveFromCoprocessor2
- arm_neon/vqshl_u8
- arm_neon/poly8_t
- arm_neon/vhadd_u16
- arm_neon/vmla_lane_u16
- arm_neon/vshrq_n_u8
- arm_neon/vuzpq_f32
- arm_neon/vmls_lane_f32
- arm_neon/vqneg_s16
- arm_neon/vtrn_p16
- arm_neon/vshrn_n_u32
- arm_neon/vaddhn_u64
- arm_neon/vabal_u32
- arm_neon/vld1q_lane_u32
- arm_neon/vrsraq_n_s32
- arm_neon/vandq_u64
- arm_neon/vqdmull_s32
- arm_neon/vext_s16
- arm_neon/vaddw_s16
- arm_neon/vrev64q_p8
- arm_neon/uint8x8x3_t
- arm_neon/vzip_f32
- armintr/_arm_ssub8
- arm_neon/uint16x4x4_t
- armintr/__swi
- armintr/_arm_smlatb
- arm_neon/vrhaddq_s8
- arm_neon/vpmax_s32
- arm_neon/vqshl_s64
- arm_neon/vrev16q_p8
- arm_neon/vqmovn_u32
- arm_neon/vld1q_f16
- arm_neon/vornq_u64
- arm_neon/vqshlq_n_s16
- arm_neon/vld1_f16
- armintr/_arm_smmlsr
- arm_neon/vshlq_s16
- arm_neon/vsubhn_s16
- arm_neon/vmulq_p8
- arm_neon/vdupq_lane_f32
- armintr/_arm_shadd16
- arm_neon/vornq_s16
- arm_neon/vst1q_lane_u8
- arm_neon/vcaleq_f32
- arm_neon/vst3q_lane_f16
- armintr/_arm_sdiv
- arm_neon/vld2_u16
- arm_neon/vdup_lane_u16
- arm_neon/vst4q_lane_f32
- arm_neon/vdup_n_f32
- arm_neon/vsubq_u8
- arm_neon/vset_lane_p16
- arm_neon/vrsqrte_f32
- arm_neon/vsubl_u8
- arm_neon/vld3q_lane_f32
- arm_neon/vqnegq_s8
- arm_neon/vqmovn_s16
- arm_neon/int16x8x3_t
- arm_neon/veorq_u16
- arm_neon/vqdmulh_n_s16
- arm_neon/vhaddq_u8
- arm_neon/vpadal_u8
- arm_neon/vst2q_s16
- arm_neon/poly16x8x4_t
- arm_neon/int64x2_t
- arm_neon/vmull_s32
- arm_neon/vld4_lane_s32
- arm_neon/vst4q_p8
- arm_neon/vmlal_lane_u16
- arm_neon/vclz_u32
- arm_neon/vsliq_n_s8
- arm_neon/vmls_n_f32
- arm_neon/vmlsl_lane_s16
- arm_neon/vst4q_u32
- arm_neon/vld1q_lane_s16
- arm_neon/vst1q_f32
- arm_neon/vrshr_n_u8
- arm_neon/vst1q_s64
- arm_neon/vbslq_u32
- arm_neon/vset_lane_s8
- arm_neon/vdupq_lane_p16
- arm_neon/vtstq_s16
- arm_neon/vshl_n_s8
- arm_neon/vqrdmulhq_n_s16
- arm_neon/vget_high_f16
- arm_neon/vst4_lane_u32
- arm_neon/vraddhn_s16
- arm_neon/vmlsl_lane_s32
- arm_neon/vld3q_s32
- arm_neon/vsriq_n_u64
- arm_neon/vld4_dup_u8
- arm_neon/vld4q_s8
- arm_neon/vqmovn_s64
- arm_neon/vrev32q_p8
- arm_neon/vsliq_n_p8
- arm_neon/vzipq_s16
- arm_neon/vgetq_lane_s64
- arm_neon/vst4_p16
- arm_neon/vsubq_u16
- arm_neon/vrev64_s32
- armintr/_arm_uhadd8
- arm_neon/vornq_u16
- arm_neon/vst4_lane_s8
- arm_neon/vabd_s32
- arm_neon/vqrdmulhq_s16
- arm_neon/vqshlq_s32
- arm_neon/int64x2x4_t
- arm_neon/vset_lane_u16
- arm_neon/vrsra_n_s32
- arm_neon/vabdl_u16
- arm_neon/vsliq_n_s32
helpviewer_keywords:
- cl.exe compiler, intrinsics
- intrinsics, ARM
ms.assetid: d3d7dadd-7bd5-4508-8bff-371a66913e20
ms.openlocfilehash: 60b766eccc768e73313dbeb430beb7a1ca70a496
ms.sourcegitcommit: e805200eaef4fe7a65a00051bbd305273af94fe7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/18/2019
ms.locfileid: "74163513"
---
# <a name="arm-intrinsics"></a>ARM 내장 함수

Microsoft C++ 컴파일러 (MSVC)는 ARM 아키텍처에서 다음 내장 함수를 사용할 수 있도록 합니다. ARM에 대 한 자세한 내용은 [Arm 개발자 설명서](https://developer.arm.com/docs) 웹 사이트의 아키텍처 및 소프트웨어 개발 도구 섹션을 참조 하세요.

##  <a name="top"></a>NEON

ARM에 대 한 NEON vector 명령 집합 확장은 x86 및 x64 아키텍처 프로세서에 공통적인 MMX 및 SSE 벡터 명령 집합에 있는 것과 유사한 Single Instruction Multiple Data (SIMD) 기능을 제공 합니다.

NEON 내장 함수는 `arm_neon.h` 헤더 파일에서 제공된 데로 지원됩니다. NEON 내장 함수에 대 한 MSVC 지원은 arm 정보 센터 웹 사이트의 [Arm 컴파일러 도구 체인 버전 4.1 컴파일러 참조](https://go.microsoft.com/fwlink/p/?LinkId=251083) 의 부록 G에 설명 되어 있는 arm 컴파일러와 유사 합니다.

MSVC와 ARM 컴파일러의 주요 차이점은 MSVC는 `vldX` `_ex` 변형을 추가 하 고 벡터 로드 및 저장 지침을 `vstX` 한다는 것입니다. `_ex` 변형은 포인터 인수의 맞춤을 지정하는 추가 매개 변수를 사용하지만 그 외에는 `_ex`가 아닌 유형과 동일합니다.

##  <a name="A"></a>ARM 관련 내장 목록

|함수 이름|지침은|함수 프로토타입|
|-------------------|-----------------|------------------------|
|_arm_smlal|SMLAL|__int64 _arm_smlal (\__int64 _RdHiLo, int _Rn, int _Rm)|
|_arm_umlal|UMLAL|unsigned __int64 _arm_umlal (unsigned \__int64 _RdHiLo, 부호 없는 int _Rn, 부호 없는 int _Rm)|
|_arm_clz|CLZ|unsigned int _arm_clz(unsigned int _Rm)|
|_arm_qadd|QADD|int _arm_qadd(int _Rm, int _Rn)|
|_arm_qdadd|QDADD|int _arm_qdadd(int _Rm, int _Rn)|
|_arm_qdsub|QDSUB|int _arm_qdsub(int _Rm, int _Rn)|
|_arm_qsub|QSUB|int _arm_qsub(int _Rm, int _Rn)|
|_arm_smlabb|SMLABB|int _arm_smlabb(int _Rn, int _Rm, int _Ra)|
|_arm_smlabt|SMLABT|int _arm_smlabt(int _Rn, int _Rm, int _Ra)|
|_arm_smlatb|SMLATB|int _arm_smlatb(int _Rn, int _Rm, int _Ra)|
|_arm_smlatt|SMLATT|int _arm_smlatt(int _Rn, int _Rm, int _Ra)|
|_arm_smlalbb|SMLALBB|__int64 _arm_smlalbb (\__int64 _RdHiLo, int _Rn, int _Rm)|
|_arm_smlalbt|SMLALBT|__int64 _arm_smlalbt (\__int64 _RdHiLo, int _Rn, int _Rm)|
|_arm_smlaltb|SMLALTB|__int64 _arm_smlaltb (\__int64 _RdHiLo, int _Rn, int _Rm)|
|_arm_smlaltt|SMLALTT|__int64 _arm_smlaltt (\__int64 _RdHiLo, int _Rn, int _Rm)|
|_arm_smlawb|SMLAWB|int _arm_smlawb(int _Rn, int _Rm, int _Ra)|
|_arm_smlawt|SMLAWT|int _arm_smlawt(int _Rn, int _Rm, int _Ra)|
|_arm_smulbb|SMULBB|int _arm_smulbb(int _Rn, int _Rm)|
|_arm_smulbt|SMULBT|int _arm_smulbt(int _Rn, int _Rm)|
|_arm_smultb|SMULTB|int _arm_smultb(int _Rn, int _Rm)|
|_arm_smultt|SMULTT|int _arm_smultt(int _Rn, int _Rm)|
|_arm_smulwb|SMULWB|int _arm_smulwb(int _Rn, int _Rm)|
|_arm_smulwt|SMULWT|int _arm_smulwt(int _Rn, int _Rm)|
|_arm_sadd16|SADD16|int _arm_sadd16(int _Rn, int _Rm)|
|_arm_sadd8|SADD8|int _arm_sadd8(int _Rn, int _Rm)|
|_arm_sasx|SASX|int _arm_sasx(int _Rn, int _Rm)|
|_arm_ssax|SSAX|int _arm_ssax(int _Rn, int _Rm)|
|_arm_ssub16|SSUB16|int _arm_ssub16(int _Rn, int _Rm)|
|_arm_ssub8|SSUB8|int _arm_ssub8(int _Rn, int _Rm)|
|_arm_shadd16|SHADD16|int _arm_shadd16(int _Rn, int _Rm)|
|_arm_shadd8|SHADD8|int _arm_shadd8(int _Rn, int _Rm)|
|_arm_shasx|SHASX|int _arm_shasx(int _Rn, int _Rm)|
|_arm_shsax|SHSAX|int _arm_shsax(int _Rn, int _Rm)|
|_arm_shsub16|SHSUB16|int _arm_shsub16(int _Rn, int _Rm)|
|_arm_shsub8|SHSUB8|int _arm_shsub8(int _Rn, int _Rm)|
|_arm_qadd16|QADD16|int _arm_qadd16(int _Rn, int _Rm)|
|_arm_qadd8|QADD8|int _arm_qadd8(int _Rn, int _Rm)|
|_arm_qasx|QASX|int _arm_qasx(int _Rn, int _Rm)|
|_arm_qsax|QSAX|int _arm_qsax(int _Rn, int _Rm)|
|_arm_qsub16|QSUB16|int _arm_qsub16(int _Rn, int _Rm)|
|_arm_qsub8|QSUB8|int _arm_qsub8(int _Rn, int _Rm)|
|_arm_uadd16|UADD16|unsigned int _arm_uadd16(unsigned int _Rn, unsigned int _Rm)|
|_arm_uadd8|UADD8|unsigned int _arm_uadd8(unsigned int _Rn, unsigned int _Rm)|
|_arm_uasx|UASX|unsigned int _arm_uasx(unsigned int _Rn, unsigned int _Rm)|
|_arm_usax|USAX|unsigned int _arm_usax(unsigned int _Rn, unsigned int _Rm)|
|_arm_usub16|USUB16|unsigned int _arm_usub16(unsigned int _Rn, unsigned int _Rm)|
|_arm_usub8|USUB8|unsigned int _arm_usub8(unsigned int _Rn, unsigned int _Rm)|
|_arm_uhadd16|UHADD16|unsigned int _arm_uhadd16(unsigned int _Rn, unsigned int _Rm)|
|_arm_uhadd8|UHADD8|unsigned int _arm_uhadd8(unsigned int _Rn, unsigned int _Rm)|
|_arm_uhasx|UHASX|unsigned int _arm_uhasx(unsigned int _Rn, unsigned int _Rm)|
|_arm_uhsax|UHSAX|unsigned int _arm_uhsax(unsigned int _Rn, unsigned int _Rm)|
|_arm_uhsub16|UHSUB16|unsigned int _arm_uhsub16(unsigned int _Rn, unsigned int _Rm)|
|_arm_uhsub8|UHSUB8|unsigned int _arm_uhsub8(unsigned int _Rn, unsigned int _Rm)|
|_arm_uqadd16|UQADD16|unsigned int _arm_uqadd16(unsigned int _Rn, unsigned int _Rm)|
|_arm_uqadd8|UQADD8|unsigned int _arm_uqadd8(unsigned int _Rn, unsigned int _Rm)|
|_arm_uqasx|UQASX|unsigned int _arm_uqasx(unsigned int _Rn, unsigned int _Rm)|
|_arm_uqsax|UQSAX|unsigned int _arm_uqsax(unsigned int _Rn, unsigned int _Rm)|
|_arm_uqsub16|UQSUB16|unsigned int _arm_uqsub16(unsigned int _Rn, unsigned int _Rm)|
|_arm_uqsub8|UQSUB8|unsigned int _arm_uqsub8(unsigned int _Rn, unsigned int _Rm)|
|_arm_sxtab|SXTAB|int _arm_sxtab(int _Rn, int _Rm, unsigned int _Rotation)|
|_arm_sxtab16|SXTAB16|int _arm_sxtab16(int _Rn, int _Rm, unsigned int _Rotation)|
|_arm_sxtah|SXTAH|int _arm_sxtah(int _Rn, int _Rm, unsigned int _Rotation)|
|_arm_uxtab|UXTAB|unsigned int _arm_uxtab(unsigned int _Rn, unsigned int _Rm, unsigned int _Rotation)|
|_arm_uxtab16|UXTAB16|unsigned int _arm_uxta16b(unsigned int _Rn, unsigned int _Rm, unsigned int _Rotation)|
|_arm_uxtah|UXTAH|unsigned int _arm_uxtah(unsigned int _Rn, unsigned int _Rm, unsigned int _Rotation)|
|_arm_sxtb|SXTB|int _arm_sxtb(int _Rn, unsigned int _Rotation)|
|_arm_sxtb16|SXTB16|int _arm_sxtb16(int _Rn, unsigned int _Rotation)|
|_arm_sxth|SXTH|int _arm_sxth(int _Rn, unsigned int _Rotation)|
|_arm_uxtb|UXTB|unsigned int _arm_uxtb(unsigned int _Rn, unsigned int _Rotation)|
|_arm_uxtb16|UXTB16|unsigned int _arm_uxtb16(unsigned int _Rn, unsigned int _Rotation)|
|_arm_uxth|UXTH|unsigned int _arm_uxth(unsigned int _Rn, unsigned int _Rotation)|
|_arm_pkhbt|PKHBT|int _arm_pkhbt(int _Rn, int _Rm, unsigned int _Lsl_imm)|
|_arm_pkhtb|PKHTB|int _arm_pkhtb(int _Rn, int _Rm, unsigned int _Asr_imm)|
|_arm_usad8|USAD8|unsigned int _arm_usad8(unsigned int _Rn, unsigned int _Rm)|
|_arm_usada8|USADA8|unsigned int _arm_usada8(unsigned int _Rn, unsigned int _Rm, unsigned int _Ra)|
|_arm_ssat|SSAT|int _arm_ssat(unsigned int _Sat_imm, _int _Rn, _ARMINTR_SHIFT_T _Shift_type, unsigned int _Shift_imm)|
|_arm_usat|USAT|int _arm_usat(unsigned int _Sat_imm, _int _Rn, _ARMINTR_SHIFT_T _Shift_type, unsigned int _Shift_imm)|
|_arm_ssat16|SSAT16|int _arm_ssat16(unsigned int _Sat_imm, _int _Rn)|
|_arm_usat16|USAT16|int _arm_usat16(unsigned int _Sat_imm, _int _Rn)|
|_arm_rev|REV|unsigned int _arm_rev(unsigned int _Rm)|
|_arm_rev16|REV16|unsigned int _arm_rev16(unsigned int _Rm)|
|_arm_revsh|REVSH|unsigned int _arm_revsh(unsigned int _Rm)|
|_arm_smlad|SMLAD|int _arm_smlad(int _Rn, int _Rm, int _Ra)|
|_arm_smladx|SMLADX|int _arm_smladx(int _Rn, int _Rm, int _Ra)|
|_arm_smlsd|SMLSD|int _arm_smlsd(int _Rn, int _Rm, int _Ra)|
|_arm_smlsdx|SMLSDX|int _arm_smlsdx(int _Rn, int _Rm, int _Ra)|
|_arm_smmla|SMMLA|int _arm_smmla(int _Rn, int _Rm, int _Ra)|
|_arm_smmlar|SMMLAR|int _arm_smmlar(int _Rn, int _Rm, int _Ra)|
|_arm_smmls|SMMLS|int _arm_smmls(int _Rn, int _Rm, int _Ra)|
|_arm_smmlsr|SMMLSR|int _arm_smmlsr(int _Rn, int _Rm, int _Ra)|
|_arm_smmul|SMMUL|int _arm_smmul(int _Rn, int _Rm)|
|_arm_smmulr|SMMULR|int _arm_smmulr(int _Rn, int _Rm)|
|_arm_smlald|SMLALD|__int64 _arm_smlald (\__int64 _RdHiLo, int _Rn, int _Rm)|
|_arm_smlaldx|SMLALDX|__int64 _arm_smlaldx (\__int64 _RdHiLo, int _Rn, int _Rm)|
|_arm_smlsld|SMLSLD|__int64 _arm_smlsld (\__int64 _RdHiLo, int _Rn, int _Rm)|
|_arm_smlsldx|SMLSLDX|__int64 _arm_smlsldx (\__int64 _RdHiLo, int _Rn, int _Rm)|
|_arm_smuad|SMUAD|int _arm_smuad(int _Rn, int _Rm)|
|_arm_smuadx|SMUADX|int _arm_muadxs(int _Rn, int _Rm)|
|_arm_smusd|SMUSD|int _arm_smusd(int _Rn, int _Rm)|
|_arm_smusdx|SMUSDX|int _arm_smusdx(int _Rn, int _Rm)|
|_arm_smull|SMULL|__int64 _arm_smull(int _Rn, int _Rm)|
|_arm_umull|UMULL|unsigned __int64 _arm_umull(unsigned int _Rn, unsigned int _Rm)|
|_arm_umaal|UMAAL|unsigned __int64 _arm_umaal(unsigned int _RdLo, unsigned int _RdHi, unsigned int _Rn, unsigned int _Rm)|
|_arm_bfc|BFC|unsigned int _arm_bfc(unsigned int _Rd, unsigned int _Lsb, unsigned int _Width)|
|_arm_bfi|BFI|unsigned int _arm_bfi(unsigned int _Rd, unsigned int _Rn, unsigned int _Lsb, unsigned int _Width)|
|_arm_rbit|RBIT|unsigned int _arm_rbit(unsigned int _Rm)|
|_arm_sbfx|SBFX|int _arm_sbfx(int _Rn, unsigned int _Lsb, unsigned int _Width)|
|_arm_ubfx|UBFX|unsigned int _arm_ubfx(unsigned int _Rn, unsigned int _Lsb, unsigned int _Width)|
|_arm_sdiv|SDIV|int _arm_sdiv(int _Rn, int _Rm)|
|_arm_udiv|UDIV|unsigned int _arm_udiv(unsigned int _Rn, unsigned int _Rm)|
|__cps|CPS|void __cps(unsigned int _Ops, unsigned int _Flags, unsigned int _Mode)|
|__dmb|DMB|void __dmb(unsigned int `_Type`)<br /><br /> 명령 스트림에 메모리 장벽 작업을 삽입합니다. 매개 변수 `_Type`은 장벽이 적용하는 제한의 종류를 지정 합니다.<br /><br /> 적용할 수 있는 제한의 종류에 대 한 자세한 내용은 [메모리 장벽 제한](#BarrierRestrictions)을 참조 하세요.|
|__dsb|DSB|void __dsb(unsigned int _Type)<br /><br /> 명령 스트림에 메모리 장벽 작업을 삽입합니다. 매개 변수 `_Type`은 장벽이 적용하는 제한의 종류를 지정 합니다.<br /><br /> 적용할 수 있는 제한의 종류에 대 한 자세한 내용은 [메모리 장벽 제한](#BarrierRestrictions)을 참조 하세요.|
|__isb|ISB|void __isb(unsigned int _Type)<br /><br /> 명령 스트림에 메모리 장벽 작업을 삽입합니다. 매개 변수 `_Type`은 장벽이 적용하는 제한의 종류를 지정 합니다.<br /><br /> 적용할 수 있는 제한의 종류에 대 한 자세한 내용은 [메모리 장벽 제한](#BarrierRestrictions)을 참조 하세요.|
|__emit||void __emit (서명 되지 않은 \__int32 opcode)<br /><br /> 컴파일러로 출력된 명령 스트림에 지정된 명령을 삽입합니다.<br /><br /> `opcode`의 값은 컴파일 타임에 알려진 상수 식이어야 합니다. 명령 단어의 크기는 16비트이며 `opcode`의 최상위 16비트는 무시됩니다.<br /><br /> 컴파일러는 `opcode`의 내용을 해석 하려고 하지 않으며 삽입 된 명령이 실행 되기 전에 CPU 또는 메모리 상태를 보장 하지 않습니다.<br /><br /> 컴파일러는 삽입된 명령이 실행된 후 CPU 및 메모리 상태가 변경되지 않는다고 가정합니다. 따라서 상태를 변경 하는 지침은 컴파일러에 의해 생성 된 일반 코드에 부정적인 영향을 미칠 수 있습니다.<br /><br /> 따라서 `emit`을 사용 하 여 컴파일러가 일반적으로 처리 하지 않는 CPU 상태 (예: 보조 프로세서 상태)에 영향을 주는 명령을 삽입 하거나 `declspec(naked)`를 사용 하 여 선언 된 함수를 구현 합니다.|
|__hvc|HVC|unsigned int __hvc(unsigned int, ...)|
|__iso_volatile_load16||__int16 \__iso_volatile_load16 (const volatile \__int16 \*)<br /><br /> 자세한 내용은 [__iso_volatile_load/store 내장 함수](#IsoVolatileLoadStore)를 참조 하세요.|
|__iso_volatile_load32||__int32 \__iso_volatile_load32 (const volatile \__int32 \*)<br /><br /> 자세한 내용은 [__iso_volatile_load/store 내장 함수](#IsoVolatileLoadStore)를 참조 하세요.|
|__iso_volatile_load64||__int64 \__iso_volatile_load64 (const volatile \__int64 \*)<br /><br /> 자세한 내용은 [__iso_volatile_load/store 내장 함수](#IsoVolatileLoadStore)를 참조 하세요.|
|__iso_volatile_load8||__int8 \__iso_volatile_load8 (const volatile \__int8 \*)<br /><br /> 자세한 내용은 [__iso_volatile_load/store 내장 함수](#IsoVolatileLoadStore)를 참조 하세요.|
|__iso_volatile_store16||void __iso_volatile_store16 (휘발성 \__int16 \*, \__int16)<br /><br /> 자세한 내용은 [__iso_volatile_load/store 내장 함수](#IsoVolatileLoadStore)를 참조 하세요.|
|__iso_volatile_store32||void __iso_volatile_store32 (휘발성 \__int32 \*, \__int32)<br /><br /> 자세한 내용은 [__iso_volatile_load/store 내장 함수](#IsoVolatileLoadStore)를 참조 하세요.|
|__iso_volatile_store64||void __iso_volatile_store64 (휘발성 \__int64 \*, \__int64)<br /><br /> 자세한 내용은 [__iso_volatile_load/store 내장 함수](#IsoVolatileLoadStore)를 참조 하세요.|
|__iso_volatile_store8||void __iso_volatile_store8 (휘발성 \__int8 \*, \__int8)<br /><br /> 자세한 내용은 [__iso_volatile_load/store 내장 함수](#IsoVolatileLoadStore)를 참조 하세요.|
|__ldrexd|LDREXD|__int64 \__ldrexd (const volatile \__int64 \*)|
|__prefetch|PLD|void __cdecl \__prefetch (const void \*)<br /><br /> `PLD` 메모리 힌트를 지정된 주소 또는 그 근처에 있는 메모리에 곧 액세스할 시스템에 제공됩니다. 일부 시스템은 런타임 성능을 향상시키기 위해 해당 메모리 액세스 패턴을 최적화하도록 선택할 수 있습니다. 그러나 C++ 언어의 관점에서 함수는 눈에 띄는 효과가 없고 아무 작업도 하지 않을 수 있습니다.|
|__rdpmccntr64||부호가 없는 __int64 \__rdpmccntr64 (void)|
|__sev|SEV|void __sev(void)|
|__static_assert||void __static_assert (int, const char \*)|
|__swi|SVC|unsigned int __swi(unsigned int, ...)|
|__trap|BKPT|int __trap(int, ...)|
|__wfe|WFE|void __wfe(void)|
|__wfi|WFI|void __wfi(void)|
|_AddSatInt|QADD|int _AddSatInt(int, int)|
|_CopyDoubleFromInt64||이중 _CopyDoubleFromInt64 (\__int64)|
|_CopyFloatFromInt32||float _CopyFloatFromInt32 (\__int32)|
|_CopyInt32FromFloat||__int32 _CopyInt32FromFloat(float)|
|_CopyInt64FromDouble||__int64 _CopyInt64FromDouble(double)|
|_CountLeadingOnes||unsigned int _CountLeadingOnes(unsigned long)|
|_CountLeadingOnes64||unsigned int _CountLeadingOnes64 (unsigned \__int64)|
|_CountLeadingSigns||unsigned int _CountLeadingSigns(long)|
|_CountLeadingSigns64||unsigned int _CountLeadingSigns64 (\__int64)|
|_CountLeadingZeros||unsigned int _CountLeadingZeros(unsigned long)|
|_CountLeadingZeros64||unsigned int _CountLeadingZeros64 (unsigned \__int64)|
|_CountOneBits||unsigned int _CountOneBits(unsigned long)|
|_CountOneBits64||unsigned int _CountOneBits64 (unsigned \__int64)|
|_DAddSatInt|QDADD|int _DAddSatInt(int, int)|
|_DSubSatInt|QDSUB|int _DSubSatInt(int, int)|
|_isunordered||int _isunordered(double, double)|
|_isunorderedf||int _isunorderedf(float, float)|
|_MoveFromCoprocessor|MRC|unsigned int _MoveFromCoprocessor(unsigned int, unsigned int, unsigned int, unsigned int, unsigned int)<br /><br /> 보조 프로세서 데이터 전송 명령을 사용하여 ARM 보조 프로세서에서 데이터를 읽습니다. 자세한 내용은 [_MoveFromCoprocessor, _MoveFromCoprocessor2을](#MoveFromCo)참조 하세요.|
|_MoveFromCoprocessor2|MRC2|unsigned int _MoveFromCoprocessor2(unsigned int, unsigned int, unsigned int, unsigned int, unsigned int)<br /><br /> 보조 프로세서 데이터 전송 명령을 사용하여 ARM 보조 프로세서에서 데이터를 읽습니다. 자세한 내용은 [_MoveFromCoprocessor, _MoveFromCoprocessor2을](#MoveFromCo)참조 하세요.|
|_MoveFromCoprocessor64|MRRC|unsigned __int64 _MoveFromCoprocessor64(unsigned int, unsigned int, unsigned int)<br /><br /> 보조 프로세서 데이터 전송 명령을 사용하여 ARM 보조 프로세서에서 데이터를 읽습니다. 자세한 내용은 [_MoveFromCoprocessor64](#MoveFromCo64)를 참조 하세요.|
|_MoveToCoprocessor|MCR|void _MoveToCoprocessor(unsigned int, unsigned int, unsigned int, unsigned int, unsigned int, unsigned int)<br /><br /> 보조 프로세서 데이터 전송 명령을 사용하여 ARM 보조 프로세서에서 데이터를 읽습니다. 자세한 내용은 [_MoveToCoprocessor, _MoveToCoprocessor2을](#MoveToCo)참조 하세요.|
|_MoveToCoprocessor2|MCR2|void _MoveToCoprocessor2(unsigned int, unsigned int, unsigned int, unsigned int, unsigned int, unsigned int)<br /><br /> 보조 프로세서 데이터 전송 명령을 사용하여 ARM 보조 프로세서에서 데이터를 읽습니다. 자세한 내용은 [_MoveToCoprocessor, _MoveToCoprocessor2을](#MoveToCo)참조 하세요.|
|_MoveToCoprocessor64|MCRR|void _MoveToCoprocessor64 (unsigned \__int64, unsigned int, unsigned int, unsigned int)<br /><br /> 보조 프로세서 데이터 전송 명령을 사용하여 ARM 보조 프로세서에서 데이터를 읽습니다. 자세한 내용은 [_MoveToCoprocessor64](#MoveToCo64)를 참조 하세요.|
|_MulHigh||long _MulHigh(long, long)|
|_MulUnsignedHigh||unsigned long _MulUnsignedHigh(unsigned long, unsigned long)|
|_ReadBankedReg|MRS|int _ReadBankedReg(int _Reg)|
|_ReadStatusReg|MRS|int _ReadStatusReg(int)|
|_SubSatInt|QSUB|int _SubSatInt(int, int)|
|_WriteBankedReg|MSR|void _WriteBankedReg(int _Value, int _Reg)|
|_WriteStatusReg|MSR|void _WriteStatusReg(int, int, int)|

[[맨 위로](#top)이동]

###  <a name="BarrierRestrictions"></a>메모리 장벽 제한

`__dmb` (데이터 메모리 장벽), `__dsb` (데이터 동기화 장벽) 및 `__isb` (명령 동기화 장벽) 내장 함수는 다음의 미리 정의 된 값을 사용 하 여 공유 도메인 및 작업의 영향을 받는 액세스의 종류 측면에서 메모리 장벽 제한을 지정 합니다.

|제한 값|설명|
|-----------------------|-----------------|
|_ARM_BARRIER_SY|전체 시스템, 읽기 및 쓰기|
|_ARM_BARRIER_ST|전체 시스템, 쓰기 전용|
|_ARM_BARRIER_ISH|내부 공유 가능, 읽기 및 쓰기|
|_ARM_BARRIER_ISHST|내부 공유 가능, 쓰기 전용|
|_ARM_BARRIER_NSH|공유 불가, 읽기 및 쓰기|
|_ARM_BARRIER_NSHST|공유 불가, 쓰기 전용|
|_ARM_BARRIER_OSH|외부 공유 가능, 읽기 및 쓰기|
|_ARM_BARRIER_OSHST|외부 공유 가능, 쓰기 전용|

`__isb` 내장 함수에 대해 현재 올바른 제한은 _ARM_BARRIER_SY뿐입니다. 다른 모든 값은 아키텍처에서 예약됩니다.

###  <a name="IsoVolatileLoadStore"></a>__iso_volatile_load/store 내장 함수

이러한 내장 함수는 컴파일러 최적화가 적용 되지 않는 로드 및 저장소를 명시적으로 수행 합니다.

```C
__int16 __iso_volatile_load16(const volatile __int16 * Location);
__int32 __iso_volatile_load32(const volatile __int32 * Location);
__int64 __iso_volatile_load64(const volatile __int64 * Location);
__int8 __iso_volatile_load8(const volatile __int8 * Location);

void __iso_volatile_store16(volatile __int16 * Location, __int16 Value);
void __iso_volatile_store32(volatile __int32 * Location, __int32 Value);
void __iso_volatile_store64(volatile __int64 * Location, __int64 Value);
void __iso_volatile_store8(volatile __int8 * Location, __int8 Value);
```

#### <a name="parameters"></a>매개 변수

*위치*\
읽거나 쓸 메모리 위치의 주소입니다.

*값*\
지정 된 메모리 위치에 쓸 값입니다 (매장 내장 함수에만 해당).

#### <a name="return-value-load-intrinsics-only"></a>반환 값 (load 내장 함수 전용)

`Location`으로 지정된 메모리 위치의 값입니다.

#### <a name="remarks"></a>주의

`__iso_volatile_load8/16/32/64` 및 `__iso_volatile_store8/16/32/64` 내장 함수를 사용 하 여 컴파일러 최적화가 적용 되지 않는 메모리 액세스를 명시적으로 수행할 수 있습니다. 컴파일러는 이러한 작업의 상대적 순서를 제거, sytize 또는 변경 하지 않지만 암시적 하드웨어 메모리 장벽을 생성 하지 않습니다. 따라서 하드웨어는 여러 스레드 간의 식별할 수 있는 메모리 액세스를 여전히 다시 정렬할 수 있습니다. 보다 정확 하 게 말하자면 이러한 내장 함수는 **/volatile: iso**에서 컴파일된 다음 식과 같습니다.

```cpp
int a = __iso_volatile_load32(p);    // equivalent to: int a = *(const volatile __int32*)p;
__iso_volatile_store32(p, a);        // equivalent to: *(volatile __int32*)p = a;
```

내장 함수가 휘발성 포인터를 취하여 휘발성 변수를 수용합니다. 그러나 휘발성 포인터를 인수로 사용 하는 것은 요구 사항이 나 권장 사항이 없습니다. 이러한 작업의 의미 체계는 보통 비휘발성 형식이 사용 되는 경우와 동일 합니다.

**/Volatile: iso** 명령줄 인수에 대 한 자세한 내용은 [/Volatile (volatile 키워드 해석)](../build/reference/volatile-volatile-keyword-interpretation.md)를 참조 하세요.

###  <a name="MoveFromCo"></a>_MoveFromCoprocessor, _MoveFromCoprocessor2

이러한 내장 함수는 보조 프로세서 데이터 전송 명령을 사용하여 ARM 보조 프로세서에서 데이트를 읽습니다.

```C
int _MoveFromCoprocessor(
      unsigned int coproc,
      unsigned int opcode1,
      unsigned int crn,
      unsigned int crm,
      unsigned int opcode2
);

int _MoveFromCoprocessor2(
      unsigned int coproc,
      unsigned int opcode1,
      unsigned int crn,
      unsigned int crm,
      unsigned int opcode2
);
```

#### <a name="parameters"></a>매개 변수

*coproc*\
보조 프로세서 번호의 범위는 0에서 15 사이입니다.

*opcode1*\
보조 프로세서 관련 opcode 범위는 0에서 7 사이입니다.

*crn*\
0에서 15 사이 범위의 보조 프로세서 레지스터 번호는 첫 번째 피연산자를 명령에 지정합니다.

*crm*\
0에서 15 사이 범위의 보조 프로세서 등록 번호는 추가 소스 또는 대상 피연산자를 지정합니다.

*opcode2*\
추가 보조 프로세서 관련 opcode 범위는 0에서 7 사이입니다.

#### <a name="return-value"></a>반환 값

보조 프로세서에서 읽는 값입니다.

#### <a name="remarks"></a>주의

내장 함수의 모든 5 개 매개 변수 값은 컴파일 타임에 알려진 상수 식 이어야 합니다.

`_MoveFromCoprocessor`는 MRC 명령을 사용하며 `_MoveFromCoprocessor2`는 MRC2를 사용합니다. 매개 변수는 명령어에 직접 인코딩되는 비트 필드에 해당합니다. 매개 변수의 해석은 보조 프로세서에 따라 다릅니다. 자세한 내용은 문제가 있는 보조 프로세서에 대한 설명서를 참조하십시오.

###  <a name="MoveFromCo64"></a>_MoveFromCoprocessor64

보조 프로세서 데이터 전송 명령을 사용하여 ARM 보조 프로세서에서 데이터를 읽습니다.

```C
unsigned __int64 _MoveFromCoprocessor64(
      unsigned int coproc,
      unsigned int opcode1,
      unsigned int crm,
);
```

#### <a name="parameters"></a>매개 변수

*coproc*\
보조 프로세서 번호의 범위는 0에서 15 사이입니다.

*opcode1*\
보조 프로세서 관련 opcode 범위는 0에서 15 사이입니다.

*crm*\
0에서 15 사이 범위의 보조 프로세서 등록 번호는 추가 소스 또는 대상 피연산자를 지정합니다.

**반환 값**

보조 프로세서에서 읽는 값입니다.

#### <a name="remarks"></a>주의

내장 함수 세 개의 매개 변수 값은 컴파일 타임에 알려진 상수 식 이어야 합니다.

`_MoveFromCoprocessor64`는 MRRC 명령을 사용합니다. 매개 변수는 명령어에 직접 인코딩되는 비트 필드에 해당합니다. 매개 변수의 해석은 보조 프로세서에 따라 다릅니다. 자세한 내용은 문제가 있는 보조 프로세서에 대한 설명서를 참조하십시오.

###  <a name="MoveToCo"></a>_MoveToCoprocessor, _MoveToCoprocessor2

이러한 내장 함수는 보조 프로세서 데이터 전송 명령을 사용하여 ARM 보조 프로세서에 데이터를 씁니다.

```C
void _MoveToCoprocessor(
      unsigned int value,
      unsigned int coproc,
      unsigned int opcode1,
      unsigned int crn,
      unsigned int crm,
      unsigned int opcode2
);

void _MoveToCoprocessor2(
      unsigned int value,
      unsigned int coproc,
      unsigned int opcode1,
      unsigned int crn,
      unsigned int crm,
      unsigned int opcode2
);
```

#### <a name="parameters"></a>매개 변수

*value*\
보조 프로세서에 쓸 값입니다.

*coproc*\
보조 프로세서 번호의 범위는 0에서 15 사이입니다.

*opcode1*\
보조 프로세서 관련 opcode 범위는 0에서 7 사이입니다.

*crn*\
0에서 15 사이 범위의 보조 프로세서 레지스터 번호는 첫 번째 피연산자를 명령에 지정합니다.

*crm*\
0에서 15 사이 범위의 보조 프로세서 등록 번호는 추가 소스 또는 대상 피연산자를 지정합니다.

*opcode2*\
추가 보조 프로세서 관련 opcode 범위는 0에서 7 사이입니다.

#### <a name="return-value"></a>반환 값

없음.

#### <a name="remarks"></a>주의

내장 함수 `coproc`, `opcode1`, `crn`, `crm`및 `opcode2` 매개 변수의 값은 컴파일 타임에 알려진 상수 식 이어야 합니다.

`_MoveToCoprocessor`는 MCR 명령을 사용하며 `_MoveToCoprocessor2`는 MCR2 명령을 사용합니다. 매개 변수는 명령어에 직접 인코딩되는 비트 필드에 해당합니다. 매개 변수의 해석은 보조 프로세서에 따라 다릅니다. 자세한 내용은 문제가 있는 보조 프로세서에 대한 설명서를 참조하십시오.

###  <a name="MoveToCo64"></a>_MoveToCoprocessor64

이러한 내장 함수는 보조 프로세서 데이터 전송 명령을 사용하여 ARM 보조 프로세서에 데이터를 씁니다.

```
void _MoveFromCoprocessor64(
      unsigned __int64 value,
      unsigned int coproc,
      unsigned int opcode1,
      unsigned int crm,
);
```

#### <a name="parameters"></a>매개 변수

*coproc*\
보조 프로세서 번호의 범위는 0에서 15 사이입니다.

*opcode1*\
보조 프로세서 관련 opcode 범위는 0에서 15 사이입니다.

*crm*\
0에서 15 사이 범위의 보조 프로세서 등록 번호는 추가 소스 또는 대상 피연산자를 지정합니다.

#### <a name="return-value"></a>반환 값

없음.

#### <a name="remarks"></a>주의

내장 함수의 `coproc`, `opcode1`및 `crm` 매개 변수 값은 컴파일 타임에 알려진 상수 식 이어야 합니다.

`_MoveFromCoprocessor64`는 MCRR 명령을 사용합니다. 매개 변수는 명령어에 직접 인코딩되는 비트 필드에 해당합니다. 매개 변수의 해석은 보조 프로세서에 따라 다릅니다. 자세한 내용은 문제가 있는 보조 프로세서에 대한 설명서를 참조하십시오.

##  <a name="I"></a>다른 아키텍처의 내장 함수에 대 한 ARM 지원

다음 테이블에서는 ARM 플랫폼에서 지원되는 다른 아키텍처의 내장 함수가 나열됩니다. ARM의 내장 함수 동작이 다른 하드웨어 아키텍처의 동작과 다른 경우 추가 정보가 표시됩니다.

|함수 이름|함수 프로토타입|
|-------------------|------------------------|
|__assume|void __assume(int)|
|__code_seg|void __code_seg (const char \*)|
|__debugbreak|void (void __cdecl \__debugbreak (void)|
|__fastfail|__declspec (noreturn) void \__fastfail (unsigned int)|
|__nop|void __nop (void) **참고:** ARM 플랫폼에서이 함수는 대상 아키텍처에서 구현 된 경우 nop 명령을 생성 합니다. 그렇지 않으면 프로그램 또는 CPU의 상태를 변경 하지 않는 대체 명령이 생성 됩니다 (예: `MOV r8, r8`). 다른 하드웨어 아키텍처의 \__nop 내장 함수와 기능적으로 동일 합니다. 프로그램 또는 CPU의 상태에 영향을 주지 않는 명령이 최적화로 대상 아키텍처에서 무시 될 수 있으므로 명령은 반드시 CPU 순환을 사용 하지 않습니다. 따라서 \__nop 내장 함수를 사용 하 여 CPU가 어떻게 동작 하는지 확실 하지 않은 한 코드 시퀀스의 실행 시간을 조작 하지 마십시오. 대신 \__nop 내장 함수를 사용 하 여 다음 명령을 특정 32 비트 경계 주소에 맞출 수 있습니다.|
|__yield|void __yield (void) **참고:** ARM 플랫폼에서이 함수는 스레드가 프로그램에 부정적인 영향을 주지 않고 실행에서 일시 중단 (예: spinlock) 할 수 있는 작업을 수행 중임을 나타내는 yield 명령을 생성 합니다. 이렇게 하면 CPU가 실행 주기 동안 다른 작업을 실행할 수 있습니다.|
|_AddressOfReturnAddress|void (void \* _AddressOfReturnAddress (void)|
|_BitScanForward|unsigned char _BitScanForward (unsigned long \* _Index, unsigned long _Mask)|
|_BitScanReverse|unsigned char _BitScanReverse (unsigned long \* _Index, unsigned long _Mask)|
|_bittest|unsigned char _bittest (long const \*, long)|
|_bittestandcomplement|unsigned char _bittestandcomplement (long \*, long)|
|_bittestandreset|unsigned char _bittestandreset (long \*, long)|
|_bittestandset|unsigned char _bittestandset (long \*, long)|
|_byteswap_uint64|unsigned __int64 \__cdecl _byteswap_uint64 (unsigned \__int64)|
|_byteswap_ulong|unsigned long __cdecl _byteswap_ulong(unsigned long)|
|_byteswap_ushort|unsigned short __cdecl _byteswap_ushort(unsigned short)|
|_disable|void __cdecl _disable (void) **참고:** ARM 플랫폼에서이 함수는 cpsid 명령을 생성 합니다. 내장 함수로만 사용할 수 있습니다.|
|_enable|void __cdecl _enable (void) **참고:** ARM 플랫폼에서이 함수는 CPSIE 명령을 생성 합니다. 내장 함수로만 사용할 수 있습니다.|
|_lrotl|unsigned long __cdecl _lrotl(unsigned long, int)|
|_lrotr|unsigned long __cdecl _lrotr(unsigned long, int)|
|_ReadBarrier|void _ReadBarrier(void)|
|_ReadWriteBarrier|void _ReadWriteBarrier(void)|
|_ReturnAddress|void (void \* _ReturnAddress (void)|
|_rotl|unsigned int __cdecl _rotl(unsigned int _Value, int _Shift)|
|_rotl16|unsigned short _rotl16(unsigned short _Value, unsigned char _Shift)|
|_rotl64|unsigned __int64 \__cdecl _rotl64 (unsigned \__int64 _Value, int _Shift)|
|_rotl8|unsigned char _rotl8(unsigned char _Value, unsigned char _Shift)|
|_rotr|unsigned int __cdecl _rotr(unsigned int _Value, int _Shift)|
|_rotr16|unsigned short _rotr16(unsigned short _Value, unsigned char _Shift)|
|_rotr64|unsigned __int64 \__cdecl _rotr64 (unsigned \__int64 _Value, int _Shift)|
|_rotr8|unsigned char _rotr8(unsigned char _Value, unsigned char _Shift)|
|_setjmpex|int __cdecl _setjmpex(jmp_buf)|
|_WriteBarrier|void _WriteBarrier(void)|

[[맨 위로](#top)이동]

## <a name="interlocked-intrinsics"></a>연동 내장 함수

Interlocked 내장 함수는 원자성 읽기-수정-쓰기 작업을 수행하는데 사용되는 내장 함수 집합입니다. 일부 내장 함수는 모든 플랫폼에 공통적입니다. 여기에는 많은 숫자가 있으므로 여기에 별도로 나열 되어 있지만 해당 정의가 거의 중복 되므로 일반적인 용어로 생각 하는 것이 더 쉽습니다. 내장 함수의 이름을 사용해 정확한 동작을 파악할 수 있습니다.

다음 테이블에서는 bittest가 아닌 interlocked 내장 함수의 ARM 지원을 요약합니다. 테이블의 각 셀은 `_Interlocked`에 행의 가장 왼쪽 셀에 작업 이름 및 열의 맨 위 셀에 형식 이름을 추가하여 파생된 이름을 뜻합니다. 예를 들어 `Xor` 행과 `8` 열이 교차 하는 셀은 `_InterlockedXor8`에 해당 하 고 완벽 하 게 지원 됩니다. 대부분의 지원되는 함수에는 옵션 접미사 `_acq`, `_rel`, 및 `_nf`가 제공됩니다. `_acq` 접미사는 "acquire" 의미를 나타내며 `_rel` 접미사는 "release" 의미를 나타냅니다. `_nf` 또는 "no fence" 접미사는 ARM에 고유 하며 다음 섹션에서 설명 합니다.

||8|16|32|64개|P|
|-|-------|--------|--------|--------|-------|
|추가|없음|없음|전체|전체|없음|
|그리고|전체|전체|전체|전체|없음|
|CompareExchange|전체|전체|전체|전체|전체|
|감소|없음|전체|전체|전체|없음|
|Exchange|Partial|Partial|Partial|Partial|Partial|
|ExchangeAdd|전체|전체|전체|전체|없음|
|증가|없음|전체|전체|전체|없음|
|Or|전체|전체|전체|전체|없음|
|Xor|전체|전체|전체|전체|없음|

키:

- **Full**: 일반, `_acq`, `_rel`및 `_nf` 형식을 지원 합니다.

- **부분**: 일반, `_acq`및 `_nf` 폼을 지원 합니다.

- **없음**: 지원 되지 않음

###  <a name="nf_suffix"></a>_nf (fence 없음) 접미사

`_nf` 또는 "no fence" 접미사는 다른 세 가지 형식 (일반, `_acq`및 `_rel`)과 달리 작업이 어떤 종류의 메모리 장벽으로도 작동 하지 않음을 나타냅니다 .이는 모두 일종의 장벽으로 작동 합니다. `_nf` 폼은 여러 스레드에서 동시에 업데이트 되는 통계 카운터를 유지 관리 하는 데 사용할 수 있으며, 여러 스레드가 실행 되는 동안에는 해당 값이 사용 되지 않습니다.

### <a name="list-of-interlocked-intrinsics"></a>연동 내장 함수 목록

|함수 이름|함수 프로토타입|
|-------------------|------------------------|
|_InterlockedAdd|long _InterlockedAdd (long _volatile \*, long)|
|_InterlockedAdd64|__int64 _InterlockedAdd64 (\__int64 휘발성 \*, \__int64)|
|_InterlockedAdd64_acq|__int64 _InterlockedAdd64_acq (\__int64 휘발성 \*, \__int64)|
|_InterlockedAdd64_nf|__int64 _InterlockedAdd64_nf (\__int64 휘발성 \*, \__int64)|
|_InterlockedAdd64_rel|__int64 _InterlockedAdd64_rel (\__int64 휘발성 \*, \__int64)|
|_InterlockedAdd_acq|long _InterlockedAdd_acq (긴 휘발성 \*, long)|
|_InterlockedAdd_nf|long _InterlockedAdd_nf (긴 휘발성 \*, long)|
|_InterlockedAdd_rel|long _InterlockedAdd_rel (긴 휘발성 \*, long)|
|_InterlockedAnd|long _InterlockedAnd (긴 휘발성 \*, long)|
|_InterlockedAnd16|short _InterlockedAnd16 (short volatile \*, short)|
|_InterlockedAnd16_acq|short _InterlockedAnd16_acq (short volatile \*, short)|
|_InterlockedAnd16_nf|short _InterlockedAnd16_nf (short volatile \*, short)|
|_InterlockedAnd16_rel|short _InterlockedAnd16_rel (short volatile \*, short)|
|_InterlockedAnd64|__int64 _InterlockedAnd64 (\__int64 휘발성 \*, \__int64)|
|_InterlockedAnd64_acq|__int64 _InterlockedAnd64_acq (\__int64 휘발성 \*, \__int64)|
|_InterlockedAnd64_nf|__int64 _InterlockedAnd64_nf (\__int64 휘발성 \*, \__int64)|
|_InterlockedAnd64_rel|__int64 _InterlockedAnd64_rel (\__int64 휘발성 \*, \__int64)|
|_InterlockedAnd8|char _InterlockedAnd8 (char volatile \*, char)|
|_InterlockedAnd8_acq|char _InterlockedAnd8_acq (char volatile \*, char)|
|_InterlockedAnd8_nf|char _InterlockedAnd8_nf (char volatile \*, char)|
|_InterlockedAnd8_rel|char _InterlockedAnd8_rel (char volatile \*, char)|
|_InterlockedAnd_acq|long _InterlockedAnd_acq (긴 휘발성 \*, long)|
|_InterlockedAnd_nf|long _InterlockedAnd_nf (긴 휘발성 \*, long)|
|_InterlockedAnd_rel|long _InterlockedAnd_rel (긴 휘발성 \*, long)|
|_InterlockedCompareExchange|long __cdecl _InterlockedCompareExchange (long 휘발성 \*, long, long)|
|_InterlockedCompareExchange16|short _InterlockedCompareExchange16 (short volatile \*, short, short)|
|_InterlockedCompareExchange16_acq|short _InterlockedCompareExchange16_acq (short volatile \*, short, short)|
|_InterlockedCompareExchange16_nf|short _InterlockedCompareExchange16_nf (short volatile \*, short, short)|
|_InterlockedCompareExchange16_rel|short _InterlockedCompareExchange16_rel (short volatile \*, short, short)|
|_InterlockedCompareExchange64|__int64 _InterlockedCompareExchange64 (\__int64 휘발성 \*, \__int64, \__int64)|
|_InterlockedCompareExchange64_acq|__int64 _InterlockedCompareExchange64_acq (\__int64 휘발성 \*, \__int64, \__int64)|
|_InterlockedCompareExchange64_nf|__int64 _InterlockedCompareExchange64_nf (\__int64 휘발성 \*, \__int64, \__int64)|
|_InterlockedCompareExchange64_rel|__int64 _InterlockedCompareExchange64_rel (\__int64 휘발성 \*, \__int64, \__int64)|
|_InterlockedCompareExchange8|char _InterlockedCompareExchange8 (char volatile \*, char, char)|
|_InterlockedCompareExchange8_acq|char _InterlockedCompareExchange8_acq (char volatile \*, char, char)|
|_InterlockedCompareExchange8_nf|char _InterlockedCompareExchange8_nf (char volatile \*, char, char)|
|_InterlockedCompareExchange8_rel|char _InterlockedCompareExchange8_rel (char volatile \*, char, char)|
|_InterlockedCompareExchangePointer|void \* _InterlockedCompareExchangePointer (void \* volatile \*, void \*, void \*)|
|_InterlockedCompareExchangePointer_acq|void \* _InterlockedCompareExchangePointer_acq (void \* volatile \*, void \*, void \*)|
|_InterlockedCompareExchangePointer_nf|void \* _InterlockedCompareExchangePointer_nf (void \* volatile \*, void \*, void \*)|
|_InterlockedCompareExchangePointer_rel|void \* _InterlockedCompareExchangePointer_rel (void \* volatile \*, void \*, void \*)|
|_InterlockedCompareExchange_acq|long _InterlockedCompareExchange_acq (long volatile \*, long, long)|
|_InterlockedCompareExchange_nf|long _InterlockedCompareExchange_nf (long volatile \*, long, long)|
|_InterlockedCompareExchange_rel|long _InterlockedCompareExchange_rel (long volatile \*, long, long)|
|_InterlockedDecrement|long __cdecl _InterlockedDecrement (긴 휘발성 \*)|
|_InterlockedDecrement16|short _InterlockedDecrement16 (짧은 휘발성 \*)|
|_InterlockedDecrement16_acq|short _InterlockedDecrement16_acq (짧은 휘발성 \*)|
|_InterlockedDecrement16_nf|short _InterlockedDecrement16_nf (짧은 휘발성 \*)|
|_InterlockedDecrement16_rel|short _InterlockedDecrement16_rel (짧은 휘발성 \*)|
|_InterlockedDecrement64|__int64 _InterlockedDecrement64 (\__int64 휘발성 \*)|
|_InterlockedDecrement64_acq|__int64 _InterlockedDecrement64_acq (\__int64 휘발성 \*)|
|_InterlockedDecrement64_nf|__int64 _InterlockedDecrement64_nf (\__int64 휘발성 \*)|
|_InterlockedDecrement64_rel|__int64 _InterlockedDecrement64_rel (\__int64 휘발성 \*)|
|_InterlockedDecrement_acq|long _InterlockedDecrement_acq (긴 휘발성 \*)|
|_InterlockedDecrement_nf|long _InterlockedDecrement_nf (긴 휘발성 \*)|
|_InterlockedDecrement_rel|long _InterlockedDecrement_rel (긴 휘발성 \*)|
|_InterlockedExchange|long __cdecl _InterlockedExchange (long 휘발성 \* _Target, long)|
|_InterlockedExchange16|short _InterlockedExchange16 (짧은 휘발성 \* _Target, short)|
|_InterlockedExchange16_acq|short _InterlockedExchange16_acq (짧은 휘발성 \* _Target, short)|
|_InterlockedExchange16_nf|short _InterlockedExchange16_nf (짧은 휘발성 \* _Target, short)|
|_InterlockedExchange64|__int64 _InterlockedExchange64 (\__int64 휘발성 \* _Target, \__int64)|
|_InterlockedExchange64_acq|__int64 _InterlockedExchange64_acq (\__int64 휘발성 \* _Target, \__int64)|
|_InterlockedExchange64_nf|__int64 _InterlockedExchange64_nf (\__int64 휘발성 \* _Target, \__int64)|
|_InterlockedExchange8|char _InterlockedExchange8 (char volatile \* _Target, char)|
|_InterlockedExchange8_acq|char _InterlockedExchange8_acq (char volatile \* _Target, char)|
|_InterlockedExchange8_nf|char _InterlockedExchange8_nf (char volatile \* _Target, char)|
|_InterlockedExchangeAdd|long __cdecl _InterlockedExchangeAdd (long 휘발성 \*, long)|
|_InterlockedExchangeAdd16|short _InterlockedExchangeAdd16 (short volatile \*, short)|
|_InterlockedExchangeAdd16_acq|short _InterlockedExchangeAdd16_acq (short volatile \*, short)|
|_InterlockedExchangeAdd16_nf|short _InterlockedExchangeAdd16_nf (short volatile \*, short)|
|_InterlockedExchangeAdd16_rel|short _InterlockedExchangeAdd16_rel (short volatile \*, short)|
|_InterlockedExchangeAdd64|__int64 _InterlockedExchangeAdd64 (\__int64 휘발성 \*, \__int64)|
|_InterlockedExchangeAdd64_acq|__int64 _InterlockedExchangeAdd64_acq (\__int64 휘발성 \*, \__int64)|
|_InterlockedExchangeAdd64_nf|__int64 _InterlockedExchangeAdd64_nf (\__int64 휘발성 \*, \__int64)|
|_InterlockedExchangeAdd64_rel|__int64 _InterlockedExchangeAdd64_rel (\__int64 휘발성 \*, \__int64)|
|_InterlockedExchangeAdd8|char _InterlockedExchangeAdd8 (char volatile \*, char)|
|_InterlockedExchangeAdd8_acq|char _InterlockedExchangeAdd8_acq (char volatile \*, char)|
|_InterlockedExchangeAdd8_nf|char _InterlockedExchangeAdd8_nf (char volatile \*, char)|
|_InterlockedExchangeAdd8_rel|char _InterlockedExchangeAdd8_rel (char volatile \*, char)|
|_InterlockedExchangeAdd_acq|long _InterlockedExchangeAdd_acq (긴 휘발성 \*, long)|
|_InterlockedExchangeAdd_nf|long _InterlockedExchangeAdd_nf (긴 휘발성 \*, long)|
|_InterlockedExchangeAdd_rel|long _InterlockedExchangeAdd_rel (긴 휘발성 \*, long)|
|_InterlockedExchangePointer|void \* _InterlockedExchangePointer (void \* volatile \* _Target, void \*)|
|_InterlockedExchangePointer_acq|void \* _InterlockedExchangePointer_acq (void \* volatile \* _Target, void \*)|
|_InterlockedExchangePointer_nf|void \* _InterlockedExchangePointer_nf (void \* volatile \* _Target, void \*)|
|_InterlockedExchange_acq|long _InterlockedExchange_acq (긴 휘발성 \* _Target, long)|
|_InterlockedExchange_nf|long _InterlockedExchange_nf (긴 휘발성 \* _Target, long)|
|_InterlockedIncrement|long __cdecl _InterlockedIncrement (긴 휘발성 \*)|
|_InterlockedIncrement16|short _InterlockedIncrement16 (짧은 휘발성 \*)|
|_InterlockedIncrement16_acq|short _InterlockedIncrement16_acq (짧은 휘발성 \*)|
|_InterlockedIncrement16_nf|short _InterlockedIncrement16_nf (짧은 휘발성 \*)|
|_InterlockedIncrement16_rel|short _InterlockedIncrement16_rel (짧은 휘발성 \*)|
|_InterlockedIncrement64|__int64 _InterlockedIncrement64 (\__int64 휘발성 \*)|
|_InterlockedIncrement64_acq|__int64 _InterlockedIncrement64_acq (\__int64 휘발성 \*)|
|_InterlockedIncrement64_nf|__int64 _InterlockedIncrement64_nf (\__int64 휘발성 \*)|
|_InterlockedIncrement64_rel|__int64 _InterlockedIncrement64_rel (\__int64 휘발성 \*)|
|_InterlockedIncrement_acq|long _InterlockedIncrement_acq (긴 휘발성 \*)|
|_InterlockedIncrement_nf|long _InterlockedIncrement_nf (긴 휘발성 \*)|
|_InterlockedIncrement_rel|long _InterlockedIncrement_rel (긴 휘발성 \*)|
|_InterlockedOr|long _InterlockedOr (긴 휘발성 \*, long)|
|_InterlockedOr16|short _InterlockedOr16 (short volatile \*, short)|
|_InterlockedOr16_acq|short _InterlockedOr16_acq (short volatile \*, short)|
|_InterlockedOr16_nf|short _InterlockedOr16_nf (short volatile \*, short)|
|_InterlockedOr16_rel|short _InterlockedOr16_rel (short volatile \*, short)|
|_InterlockedOr64|__int64 _InterlockedOr64 (\__int64 휘발성 \*, \__int64)|
|_InterlockedOr64_acq|__int64 _InterlockedOr64_acq (\__int64 휘발성 \*, \__int64)|
|_InterlockedOr64_nf|__int64 _InterlockedOr64_nf (\__int64 휘발성 \*, \__int64)|
|_InterlockedOr64_rel|__int64 _InterlockedOr64_rel (\__int64 휘발성 \*, \__int64)|
|_InterlockedOr8|char _InterlockedOr8 (char volatile \*, char)|
|_InterlockedOr8_acq|char _InterlockedOr8_acq (char volatile \*, char)|
|_InterlockedOr8_nf|char _InterlockedOr8_nf (char volatile \*, char)|
|_InterlockedOr8_rel|char _InterlockedOr8_rel (char volatile \*, char)|
|_InterlockedOr_acq|long _InterlockedOr_acq (긴 휘발성 \*, long)|
|_InterlockedOr_nf|long _InterlockedOr_nf (긴 휘발성 \*, long)|
|_InterlockedOr_rel|long _InterlockedOr_rel (긴 휘발성 \*, long)|
|_InterlockedXor|long _InterlockedXor (긴 휘발성 \*, long)|
|_InterlockedXor16|short _InterlockedXor16 (short volatile \*, short)|
|_InterlockedXor16_acq|short _InterlockedXor16_acq (short volatile \*, short)|
|_InterlockedXor16_nf|short _InterlockedXor16_nf (short volatile \*, short)|
|_InterlockedXor16_rel|short _InterlockedXor16_rel (short volatile \*, short)|
|_InterlockedXor64|__int64 _InterlockedXor64 (\__int64 휘발성 \*, \__int64)|
|_InterlockedXor64_acq|__int64 _InterlockedXor64_acq (\__int64 휘발성 \*, \__int64)|
|_InterlockedXor64_nf|__int64 _InterlockedXor64_nf (\__int64 휘발성 \*, \__int64)|
|_InterlockedXor64_rel|__int64 _InterlockedXor64_rel (\__int64 휘발성 \*, \__int64)|
|_InterlockedXor8|char _InterlockedXor8 (char volatile \*, char)|
|_InterlockedXor8_acq|char _InterlockedXor8_acq (char volatile \*, char)|
|_InterlockedXor8_nf|char _InterlockedXor8_nf (char volatile \*, char)|
|_InterlockedXor8_rel|char _InterlockedXor8_rel (char volatile \*, char)|
|_InterlockedXor_acq|long _InterlockedXor_acq (긴 휘발성 \*, long)|
|_InterlockedXor_nf|long _InterlockedXor_nf (긴 휘발성 \*, long)|
|_InterlockedXor_rel|long _InterlockedXor_rel (긴 휘발성 \*, long)|

[[맨 위로](#top)이동]

### <a name="_interlockedbittest-intrinsics"></a>_interlockedbittest 내장 함수

일반 연동 비트 테스트 내장 함수는 모든 플랫폼에 공통적입니다. ARM은이 문서의 앞부분에 있는 [_nf (fence 없음) 접미사](#nf_suffix) 에 설명 된 대로 작업의 장애물 의미 체계를 수정 하는 `_acq`, `_rel`및 `_nf` 변형을 추가 합니다.

|함수 이름|함수 프로토타입|
|-------------------|------------------------|
|_interlockedbittestandreset|unsigned char _interlockedbittestandreset (long volatile \*, long)|
|_interlockedbittestandreset_acq|unsigned char _interlockedbittestandreset_acq (long volatile \*, long)|
|_interlockedbittestandreset_nf|unsigned char _interlockedbittestandreset_nf (long volatile \*, long)|
|_interlockedbittestandreset_rel|unsigned char _interlockedbittestandreset_rel (long volatile \*, long)|
|_interlockedbittestandset|unsigned char _interlockedbittestandset (long volatile \*, long)|
|_interlockedbittestandset_acq|unsigned char _interlockedbittestandset_acq (long volatile \*, long)|
|_interlockedbittestandset_nf|unsigned char _interlockedbittestandset_nf (long volatile \*, long)|
|_interlockedbittestandset_rel|unsigned char _interlockedbittestandset_rel (long volatile \*, long)|

[[맨 위로](#top)이동]

## <a name="see-also"></a>참조

[컴파일러 내장 함수](../intrinsics/compiler-intrinsics.md)\
[ARM64 내장 함수](arm64-intrinsics.md)\
[ARM 어셈블러 참조](../assembler/arm/arm-assembler-reference.md)\
[C++언어 참조](../cpp/cpp-language-reference.md)
