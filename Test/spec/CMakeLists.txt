ADD_WAST_TESTS(
	SOURCES address.wast
			align.wast
			atomic.wast
			binary.wast
			binary-leb128.wast
			block.wast
			br.wast
			br_if.wast
			br_table.wast
			bulk.wast
			call.wast
			call_indirect.wast
			comments.wast
			const.wast
			conversions.wast
			custom.wast
			data.wast
			elem.wast
			endianness.wast
			exports.wast
			f32.wast
			f32_bitwise.wast
			f32_cmp.wast
			f64.wast
			f64_bitwise.wast
			f64_cmp.wast
			fac.wast
			float_exprs.wast
			float_literals.wast
			float_memory.wast
			float_misc.wast
			forward.wast
			func.wast
			func_ptrs.wast
			globals.wast
			i32.wast
			i64.wast
			if.wast
			imports.wast
			inline-module.wast
			int_exprs.wast
			int_literals.wast
			labels.wast
			left-to-right.wast
			linking.wast
			load.wast
			local_get.wast
			local_set.wast
			local_tee.wast
			loop.wast
			memory.wast
			memory_copy.wast
			memory_fill.wast
			memory_grow.wast
			memory_init.wast
			memory_redundancy.wast
			memory_size.wast
			memory_trap.wast
			names.wast
			nop.wast
			ref_func.wast
			ref_is_null.wast
			ref_null.wast
			return.wast
			select.wast
			skip-stack-guard-page.wast
			start.wast
			stack.wast
			store.wast
			switch.wast
			table_copy.wast
			table_fill.wast
			table_get.wast
			table_grow.wast
			table_init.wast
			table_set.wast
			table_size.wast
			token.wast
			traps.wast
			type.wast
			unreachable.wast
			unreached-invalid.wast
			unwind.wast
			utf8-invalid-encoding.wast
			utf8-custom-section-id.wast
			utf8-import-field.wast
			utf8-import-module.wast
	WAVM_ARGS "--test-cloning")

add_subdirectory(simd)

if(WAVM_ENABLE_RUNTIME)
	if(CMAKE_SYSTEM_PROCESSOR STREQUAL "aarch64")
		# Can't use WILL_FAIL, since it doesn't expect tests that crash.
		set_tests_properties(skip-stack-guard-page.wast PROPERTIES DISABLED true)
	endif()
endif()
