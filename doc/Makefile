.PHONY:    default clean tarball

core = client debug globals mouse players text

interfaces = actionbar bankscreen interfaces mainscreen minimap

gametabs = abilitybook backpack gametab logout
lobby = lobby worlds

items = items

misc = smart
objects = 
utilities = color drawing pixelshift time wrappers
types = extendedarrays string tbox tpointarrays integerarrays stringarrays tpoint types



all:
	@python docgen.py `echo $(core) | sed -r \
		's/(\w+)/..\/lib\/core\/\1.simba/g'` > /dev/null
	@python docgen.py `echo $(interfaces) | sed -r \
		's/(\w+)/..\/lib\/interfaces\/\1.simba/g'` > /dev/null
	@python docgen.py `echo $(gametabs) | sed -r \
		's/(\w+)/..\/lib\/interfaces\/gametabs\/\1.simba/g'` > /dev/null
	@python docgen.py `echo $(lobby) | sed -r \
		's/(\w+)/..\/lib\/interfaces\/lobby\/\1.simba/g'` > /dev/null
	@python docgen.py `echo $(items) | sed -r \
		's/(\w+)/..\/lib\/items\/\1.simba/g'` > /dev/null
	@python docgen.py `echo $(misc) | sed -r \
		's/(\w+)/..\/lib\/misc\/\1.simba/g'` > /dev/null
	@python docgen.py `echo $(objects) | sed -r \
		's/(\w+)/..\/lib\/objects\/\1.simba/g'` > /dev/null
	@python docgen.py `echo $(utilities) | sed -r \
		's/(\w+)/..\/lib\/utilities\/\1.simba/g'` > /dev/null
	@python docgen.py `echo $(types) | sed -r \
		's/(\w+)/..\/lib\/utilities\/types\/\1.simba/g'` > /dev/null
	@make -C sphinx/ html

clean:
	rm -f `echo $(core) | sed -r 's/(\w+)/sphinx\/\1.rst/g'`
	rm -f `echo $(interfaces) | sed -r 's/(\w+)/sphinx\/\1.rst/g'`
	rm -f `echo $(gametabs) | sed -r 's/(\w+)/sphinx\/\1.rst/g'`
	rm -f `echo $(lobby) | sed -r 's/(\w+)/sphinx\/\1.rst/g'`
	rm -f `echo $(items) | sed -r 's/(\w+)/sphinx\/\1.rst/g'`
	rm -f `echo $(misc) | sed -r 's/(\w+)/sphinx\/\1.rst/g'`
	rm -f `echo $(objects) | sed -r 's/(\w+)/sphinx\/\1.rst/g'`
	rm -f `echo $(utilities) | sed -r 's/(\w+)/sphinx\/\1.rst/g'`
	rm -f `echo $(types) | sed -r 's/(\w+)/sphinx\/\1.rst/g'`
	@make -C sphinx/ clean

tarball:
	@$(MAKE) all
	@tar cjf doc.tar.bz2 -C sphinx/_build/ html