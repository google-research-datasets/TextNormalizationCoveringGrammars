all: en/verbalizer/verbalizer.far ru/verbalizer/verbalizer.far


# Language-universal definitions.

universal/thousands_punct.far: universal/thousands_punct.grm util/byte.far util/util.far
	thraxcompiler --input_grammar=$< --output_far=$@

util/util.far: util/util.grm util/byte.far util/case.far
	thraxcompiler --input_grammar=$< --output_far=$@

util/byte.far: util/byte.grm 
	thraxcompiler --input_grammar=$< --output_far=$@

util/case.far: util/case.grm util/byte.far
	thraxcompiler --input_grammar=$< --output_far=$@

util/arithmetic.far: util/arithmetic.grm util/germanic.tsv util/byte.far
	thraxcompiler --input_grammar=$< --output_far=$@

# English verbalizer.

en/verbalizer/verbalizer.far: en/verbalizer/verbalizer.grm util/util.far en/verbalizer/extra_numbers.far en/verbalizer/float.far en/verbalizer/math.far en/verbalizer/miscellaneous.far en/verbalizer/money.far en/verbalizer/numbers.far en/verbalizer/numbers_plus.far en/verbalizer/spelled.far en/verbalizer/spoken_punct.far en/verbalizer/time.far en/verbalizer/urls.far
	thraxcompiler --input_grammar=$< --output_far=$@

en/verbalizer/number_names.far: en/verbalizer/number_names.grm en/verbalizer/cardinals.tsv en/verbalizer/g.fst en/verbalizer/ordinals.tsv util/arithmetic.far
	thraxcompiler --input_grammar=$< --output_far=$@

en/verbalizer/extra_numbers.far: en/verbalizer/extra_numbers.grm util/byte.far en/verbalizer/numbers.far
	thraxcompiler --input_grammar=$< --output_far=$@

en/verbalizer/numbers.far: en/verbalizer/numbers.grm en/verbalizer/number_names.far util/byte.far universal/thousands_punct.far
	thraxcompiler --input_grammar=$< --output_far=$@

en/verbalizer/float.far: en/verbalizer/float.grm en/verbalizer/factorization.far en/verbalizer/lexical_map.far en/verbalizer/numbers.far
	thraxcompiler --input_grammar=$< --output_far=$@

en/verbalizer/factorization.far: en/verbalizer/factorization.grm util/byte.far util/util.far en/verbalizer/numbers.far
	thraxcompiler --input_grammar=$< --output_far=$@

en/verbalizer/lexical_map.far: en/verbalizer/lexical_map.grm util/byte.far en/verbalizer/lexical_map.tsv
	thraxcompiler --input_grammar=$< --output_far=$@

en/verbalizer/math.far: en/verbalizer/math.grm en/verbalizer/float.far en/verbalizer/lexical_map.far en/verbalizer/numbers.far
	thraxcompiler --input_grammar=$< --output_far=$@

en/verbalizer/miscellaneous.far: en/verbalizer/miscellaneous.grm util/byte.far ru/classifier/cyrillic.far en/verbalizer/extra_numbers.far en/verbalizer/lexical_map.far en/verbalizer/numbers.far en/verbalizer/spelled.far
	thraxcompiler --input_grammar=$< --output_far=$@

en/verbalizer/spelled.far: en/verbalizer/spelled.grm util/byte.far ru/classifier/cyrillic.far en/verbalizer/lexical_map.far en/verbalizer/numbers.far
	thraxcompiler --input_grammar=$< --output_far=$@

en/verbalizer/money.far: en/verbalizer/money.grm util/byte.far en/verbalizer/lexical_map.far en/verbalizer/numbers.far en/verbalizer/money.tsv
	thraxcompiler --input_grammar=$< --output_far=$@

en/verbalizer/numbers_plus.far: en/verbalizer/numbers_plus.grm en/verbalizer/factorization.far en/verbalizer/lexical_map.far en/verbalizer/numbers.far
	thraxcompiler --input_grammar=$< --output_far=$@

en/verbalizer/spoken_punct.far: en/verbalizer/spoken_punct.grm en/verbalizer/lexical_map.far
	thraxcompiler --input_grammar=$< --output_far=$@

en/verbalizer/time.far: en/verbalizer/time.grm util/byte.far en/verbalizer/lexical_map.far en/verbalizer/numbers.far
	thraxcompiler --input_grammar=$< --output_far=$@

en/verbalizer/urls.far: en/verbalizer/urls.grm util/byte.far en/verbalizer/lexical_map.far
	thraxcompiler --input_grammar=$< --output_far=$@


# Russian verbalizer.

ru/verbalizer/verbalizer.far: ru/verbalizer/verbalizer.grm util/util.far ru/verbalizer/extra_numbers.far ru/verbalizer/float.far ru/verbalizer/math.far ru/verbalizer/miscellaneous.far ru/verbalizer/money.far ru/verbalizer/numbers.far ru/verbalizer/numbers_plus.far ru/verbalizer/spelled.far ru/verbalizer/spoken_punct.far ru/verbalizer/time.far ru/verbalizer/urls.far
	thraxcompiler --input_grammar=$< --output_far=$@

ru/verbalizer/number_names.far: ru/verbalizer/number_names.grm ru/verbalizer/cardinals.tsv ru/verbalizer/g.fst ru/verbalizer/ordinals.tsv util/arithmetic.far
	thraxcompiler --input_grammar=$< --output_far=$@

ru/verbalizer/extra_numbers.far: ru/verbalizer/extra_numbers.grm util/byte.far ru/verbalizer/numbers.far
	thraxcompiler --input_grammar=$< --output_far=$@

ru/verbalizer/numbers.far: ru/verbalizer/numbers.grm util/byte.far universal/thousands_punct.far ru/verbalizer/nominatives.tsv ru/verbalizer/number_names.far
	thraxcompiler --input_grammar=$< --output_far=$@

ru/verbalizer/cardinals-lex.far: ru/verbalizer/cardinals-lex.grm util/byte.far
	thraxcompiler --input_grammar=$< --output_far=$@

ru/verbalizer/ordinals-lex.far: ru/verbalizer/ordinals-lex.grm util/byte.far
	thraxcompiler --input_grammar=$< --output_far=$@

ru/verbalizer/float.far: ru/verbalizer/float.grm ru/verbalizer/factorization.far ru/verbalizer/lexical_map.far ru/verbalizer/numbers.far
	thraxcompiler --input_grammar=$< --output_far=$@

ru/verbalizer/factorization.far: ru/verbalizer/factorization.grm util/byte.far util/util.far ru/verbalizer/numbers.far
	thraxcompiler --input_grammar=$< --output_far=$@

ru/verbalizer/lexical_map.far: ru/verbalizer/lexical_map.grm util/byte.far
	thraxcompiler --input_grammar=$< --output_far=$@

ru/verbalizer/math.far: ru/verbalizer/math.grm ru/verbalizer/float.far ru/verbalizer/lexical_map.far ru/verbalizer/numbers.far
	thraxcompiler --input_grammar=$< --output_far=$@

ru/verbalizer/miscellaneous.far: ru/verbalizer/miscellaneous.grm util/byte.far ru/classifier/cyrillic.far ru/verbalizer/extra_numbers.far ru/verbalizer/lexical_map.far ru/verbalizer/numbers.far ru/verbalizer/spelled.far
	thraxcompiler --input_grammar=$< --output_far=$@

ru/classifier/cyrillic.far: ru/classifier/cyrillic.grm 
	thraxcompiler --input_grammar=$< --output_far=$@

ru/verbalizer/spelled.far: ru/verbalizer/spelled.grm util/byte.far ru/classifier/cyrillic.far ru/verbalizer/lexical_map.far ru/verbalizer/numbers.far
	thraxcompiler --input_grammar=$< --output_far=$@

ru/verbalizer/money.far: ru/verbalizer/money.grm util/byte.far ru/verbalizer/lexical_map.far ru/verbalizer/numbers.far ru/verbalizer/money.tsv
	thraxcompiler --input_grammar=$< --output_far=$@

ru/verbalizer/numbers_plus.far: ru/verbalizer/numbers_plus.grm ru/verbalizer/factorization.far ru/verbalizer/lexical_map.far ru/verbalizer/numbers.far
	thraxcompiler --input_grammar=$< --output_far=$@

ru/verbalizer/spoken_punct.far: ru/verbalizer/spoken_punct.grm ru/verbalizer/lexical_map.far
	thraxcompiler --input_grammar=$< --output_far=$@

ru/verbalizer/time.far: ru/verbalizer/time.grm util/byte.far ru/verbalizer/lexical_map.far ru/verbalizer/numbers.far
	thraxcompiler --input_grammar=$< --output_far=$@

ru/verbalizer/urls.far: ru/verbalizer/urls.grm util/byte.far ru/verbalizer/lexical_map.far
	thraxcompiler --input_grammar=$< --output_far=$@


# Cleanup.

clean:
	$(RM) */*.far */*/*.far
