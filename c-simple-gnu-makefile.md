# C SIMPLE GNU MAKEFILE
```
CSRC = $(wildcard *.c)
CPPSRC = $(wildcard *.cpp)

CLEANF :=

all:

CFLAGS ?= -O2 -g -fomit-frame-pointer -Wall -Wextra

ifeq ($(V),)
CCS=@echo "   CC " $@ && $(CC)
CXXS=@echo "  CXX " $@ && $(CXX)
else
CCS=$(CC)
CXXS=$(CXX)
endif

CCMD = $$(CCS) $$(CFLAGS) $$< -o $$@
CPPCMD = $$(CXXS) $$(CFLAGS) $$< -o $$@

define MAKEPROG

$(basename $(1)): $(1)
    $(2) $$($(basename $(1))_CFLAGS)

all: $(basename $(1))

CLEANF += $(basename $(1))

endef

clean:
    @echo "  RM " $@ && $(RM) $(CLEANF)

$(foreach SRC,$(CSRC),\
    $(eval $(call MAKEPROG,$(SRC),$(CCMD))))

$(foreach SRC,$(CPPSRC),\
    $(eval $(call MAKEPROG,$(SRC),$(CPPCMD))))
```
